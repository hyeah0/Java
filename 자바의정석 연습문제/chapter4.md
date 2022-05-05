### 자바의 정석 chapter 4 연습문제

#### 4-7 charAT(int i) 활용

1.  charAT(int i) 메서드는 문자열에서 i번째 문자를 반환한다
    테이블 생성

        	String text = "hello";

        	for(int b=0; b < text.length(); b++) {
        		System.out.println("str.charAt("+ b + ") = "+text.charAt(b));
        	}

            str.charAt(0) = h
            str.charAt(1) = e
            str.charAt(2) = l
            str.charAt(3) = l
            str.charAt(4) = o

2.  문자열이 "12345" 라면 1+2+3+4+5 의 결과를 만들기

        String str = "12345";
        int sum = 0;

        for(int a=0; a < str.length(); a++) {
        sum += str.charAt(a) - '0'
        System.out.println("str.charAt(a) - '0' = "+str.charAt(a)- '0');
        }
        System.out.println("sum="+sum);

        str.charAt(0) = 1 <- "12345" 에서 idx 0 번 문자
        str.charAt(1) = 2 <- "12345" 에서 idx 1 번 문자
        str.charAt(2) = 3 <- "12345" 에서 idx 2 번 문자
        str.charAt(3) = 4 <- "12345" 에서 idx 3 번 문자
        str.charAt(4) = 5 <- "12345" 에서 idx 4 번 문자

        str.charAt(0) - '0' = 1
        설명 1 "12345" 에서 idx 0 번 문자 1의 문자코드 49 - 0 문자코드 48을 뺀 값 = 1
        설명 2 '1'-'0' -> 49 - 48 = 1
        str.charAt(1) - '0' = 2
        str.charAt(2) - '0' = 3
        str.charAt(3) - '0' = 4
        str.charAt(4) - '0' = 5

| 문자 | 문자코드 |
| ---- | -------- |
| 0    | 48       |
| 1    | 49       |
| 2    | 50       |
| 3    | 51       |
| 4    | 52       |

#### 4-8 Math.random() 활용

1.  Math.random() 값은 0.123455677 랜덤 실수로 나타난다.
2.  실수를 정수로 나타내고 싶을때

    int value =(int) (Math.random);
    (정수를 실수로 나타내고 싶을때는 따로 설정 안해도 된다.)
    double value = 1;

3.  랜덤한 숫자를 a~c 사이의 값을 받고 싶을 경우 랜덤 값에 c 값을 곱하고 +1을 한다 (+1을 안할경우 c -1 값 까지 랜덤 수가 나온다.)

    (Math.random() \* c) + 1

        System.out.println("Math.random()을 이용하여 1부터 6사이의 임의의 정수를 변수 value에 저장하는 코드를 완성하라");
        int value =(int) (Math.random()\*6)+1;

#### 4-9 % , / 활용

    int타입의 변수 num 이 있을 때, 각 자리의 합을 더한 결과를 출력하는 코드를 완 성하라.
    만일 변수 num의 값이 12345라면, ‘1+2+3+4+5’의 결과인 15를 출력하라.

    int num = 12345;

    num%10 = num을 10으로 나눈 나머지값
    num/10 = num을 10으로 나눈 값

    int num = 12345;
    	int sum = 0;

    	while(num>0) {
    		sum += num%10;
    		num /= 10; //num을 10으로 나눈다
    		System.out.println(num);

    	}
    	System.out.println(sum);

#### 4-10 작성값 입력하기

1.  import java.util.Scanner;

    import java.util.Scanner;
    Scanner scanner = new Scanner(System.in);
    String tmp = scanner.nextLine();
    int inputNum = Integer.parseInt(tmp);

2.  java.util.Scanner s = new java.util.Scanner(System.in);

    java.util.Scanner s = new java.util.Scanner(System.in);
    inputNum = s.nextInt();

    > 예시

    [4-10] 다음은 숫자맞추기 게임을 작성한 것이다.
    1과 100사이의 값을 반복적으로 입력 해서 컴퓨터가 생각한 값을 맞추면 게임이 끝난다.
    사용자가 값을 입력하면, 컴퓨터는 자 신이 생각한 값과 비교해서 결과를 알려준다.
    사용자가 컴퓨터가 생각한 숫자를 맞추면 게임이 끝나고 몇 번 만에 숫자를 맞췄는지 알려준다.

        package d4_practiceTests;

        1번 방법 import java.util.Scanner;

        public class Ex10 {

         public static void main(String[] args) {

             int randomNum = (int)(Math.random()*100)+1;
             System.out.println(randomNum);
             int count = 0;
             int inputNum = 0;

             while(true){
             System.out.print("1에서 100까지 랜덤한 숫자를 입력하세요 > ");

             1번 방법 Scanner scanner = new Scanner(System.in);
             1번 방법 String tmp = scanner.nextLine();
             1번 방법 int inputNum = Integer.parseInt(tmp);

             2번 방법 java.util.Scanner s = new java.util.Scanner(System.in);
             2번 방법 inputNum = s.nextInt();
             count++;
             if(inputNum > randomNum) {
             System.out.println("정답이 아닙니다 더 작은 수를 입력하세요");
             }
             else if(inputNum < randomNum) {
             System.out.println("정답이 아닙니다 더 큰 수를 입력하세요");
             }
             else {
             System.out.println("정답입니다");
             System.out.println("정답을 " + count + "번 만에 맞추셨습니다.");
             break;
             }
             }
         }

    }
