### 연습문제

- chapter7_1

  - 섯다카드 20장을 포함하는 섯다카드 한벌(SutdaDeck 클래스) 을 정의한 것이다.
    섯다카드 20장을 담는 섯다카드배열을 초기화 하시오.
    단 섯다카드는 1부터 10까지 숫자가 적힌 카드가 한쌍씩 있고, 숫자가 1,3,8인 경우에는 둘중의 한장은 광이어야한다.
    즉, 섯다카드의 인스턴스 변수 isKwang의 값이 true이어야한다.

- 결과

        1K , 2 , 3K , 4 , 5 , 6 , 7 , 8K , 9 , 10 , 1 , 2 , 3 , 4 , 5 , 6 , 7 , 8 , 9 , 10 ,

- 코드

        package pr7.pr7_1;

        class SutdaDeck{
            final int CARD_NUM =20;
            SutdaCard[] cards = new SutdaCard[CARD_NUM];

            //생성자
            SutdaDeck() {
                for(int i=0; i<cards.length; i++) {
                    int num = i%10+1;
                    boolean isKwang =(i<10)&&( num == 1 || num == 3 || num == 8 );

                    cards[i] = new SutdaCard(num,isKwang);
                }
            }
        }

        class SutdaCard{
            int num;
            boolean isKwang;

            SutdaCard(){
                this(1,true);
            }

            SutdaCard(int num, boolean isKwang){
                this.num = num;
                this.isKwang = isKwang;
            }

            public String toString() {
                return num + (isKwang? "K" : "");
            }
        }

        public class Exercise7_1 {

            public static void main(String[] args) {
                SutdaDeck deck = new SutdaDeck();
                for(int i=0; i<deck.cards.length; i++) {
                    System.out.print(deck.cards[i] + " , ");
                }

            }

        }
