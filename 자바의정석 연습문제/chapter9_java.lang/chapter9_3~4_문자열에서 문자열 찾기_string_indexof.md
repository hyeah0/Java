### 연습문제

#### chapter9_3~4 String 클래스 indexof

> indexof("aaa",0) : 문자열에서 0번째부터 확인시 "aaa"가 위치한 곳 반환
> contain("a") : 문자열에서 "a"가 포함되어있으면 true, 아닐경우 false

##### chapter9_3

주어진 문자열(src)에 찾으려는 문자열(target)이 몇번 나오는지 반환하라

- 결과

        3
        0

- 코드

        package pr9.pr9_3_count;

        public class Pr9_3 {

            public static int count(String src, String target) {
                int count = 0; // 찾은 횟수
                int pos = 0; // 찾기시작할 위치

                while(true) {
                    pos = src.indexOf(target,pos);

                    if(pos != -1) {
                        count++;
                        pos += target.length();

                    }

                    else {
                        break;
                    }
                }
                return count;
            }


            public static void main(String[] args) {
                System.out.println(count("01234AB12AB345AB","AB") );
                System.out.println(count("12345","AB");
            }

        }

###### 설명

- 설명 코드 결과

        "01234AB12AB345AB" 0 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 5번째
        count 값 : 1
        타겟 길이 : 2
        pos + 타겟길이 : 7
        "01234AB12AB345AB" 7 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 9번째
        count 값 : 2
        타겟 길이 : 2
        pos + 타겟길이 : 11
        "01234AB12AB345AB" 11 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 14번째
        count 값 : 3
        타겟 길이 : 2
        pos + 타겟길이 : 16
        "01234AB12AB345AB" 16 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : -1번째
        총 3회 포함

        "01ABC34AB12AB345AB" 0 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 2번째
        count 값 : 1
        타겟 길이 : 2
        pos + 타겟길이 : 4
        "01ABC34AB12AB345AB" 4 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 7번째
        count 값 : 2
        타겟 길이 : 2
        pos + 타겟길이 : 9
        "01ABC34AB12AB345AB" 9 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 11번째
        count 값 : 3
        타겟 길이 : 2
        pos + 타겟길이 : 13
        "01ABC34AB12AB345AB" 13 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 16번째
        count 값 : 4
        타겟 길이 : 2
        pos + 타겟길이 : 18
        "01ABC34AB12AB345AB" 18 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : -1번째
        총 4회 포함

        "01ACB34AB12AB345AB" 0 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 7번째
        count 값 : 1
        타겟 길이 : 2
        pos + 타겟길이 : 9
        "01ACB34AB12AB345AB" 9 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 11번째
        count 값 : 2
        타겟 길이 : 2
        pos + 타겟길이 : 13
        "01ACB34AB12AB345AB" 13 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : 16번째
        count 값 : 3
        타겟 길이 : 2
        pos + 타겟길이 : 18
        "01ACB34AB12AB345AB" 18 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : -1번째
        총 3회 포함

        "01ABCB34ABC12ABC345ABC" 0 번째 위치에서 부터 찾은 "ABC" 는 어디에 있는지?
        pos : 2번째
        count 값 : 1
        타겟 길이 : 3
        pos + 타겟길이 : 5
        "01ABCB34ABC12ABC345ABC" 5 번째 위치에서 부터 찾은 "ABC" 는 어디에 있는지?
        pos : 8번째
        count 값 : 2
        타겟 길이 : 3
        pos + 타겟길이 : 11
        "01ABCB34ABC12ABC345ABC" 11 번째 위치에서 부터 찾은 "ABC" 는 어디에 있는지?
        pos : 13번째
        count 값 : 3
        타겟 길이 : 3
        pos + 타겟길이 : 16
        "01ABCB34ABC12ABC345ABC" 16 번째 위치에서 부터 찾은 "ABC" 는 어디에 있는지?
        pos : 19번째
        count 값 : 4
        타겟 길이 : 3
        pos + 타겟길이 : 22
        "01ABCB34ABC12ABC345ABC" 22 번째 위치에서 부터 찾은 "ABC" 는 어디에 있는지?
        pos : -1번째
        총 4회 포함

        "12345" 0 번째 위치에서 부터 찾은 "AB" 는 어디에 있는지?
        pos : -1번째
        총 0회 포함

        "01234AB12AB345AB" 0번째 위치에서 부터 찾은 "AB"는 어디에 있는지? 5번째
        "01234AB12AB345AB" 7번째 위치에서 부터 찾은 "AB"는 어디에 있는지? 9번째

- 설명 코드

        package pr9.pr9_3_count;

        public class Pr9_3 {

            public static int count(String src, String target) {
                int count = 0; // 찾은 횟수
                int pos = 0; // 찾기시작할 위치

                while(true) {
                    //1.src에서 target을 pos의 위치부터 찾는다.
                    System.out.println("\""+src + "\" " + pos + " 번째 위치에서 부터 찾은 \"" + target +"\" 는 어디에 있는지? ");
                    pos = src.indexOf(target,pos);
                    System.out.println("pos : " + pos + "번째");

                    //2. 찾으면 count값을 1 증가시키고, pos 값을 target.length만큼 증가시킨다.
                    if(pos != -1) {
                        count++;
                        pos += target.length();
                        System.out.println("count 값 : " + count);
                        System.out.println("타겟 길이 : " + target.length());
                        System.out.println("pos + 타겟길이 : " + pos);

                    }
                    //3. indexof의 결과가 -1이면 반복문 종료
                    else {
                        break;
                    }
                }
                return count;
            }


            public static void main(String[] args) {
                System.out.println("총 " + count("01234AB12AB345AB","AB") + "회 포함 \n");
                System.out.println("총 " + count("01ABC34AB12AB345AB","AB") + "회 포함\n");
                System.out.println("총 " + count("01ACB34AB12AB345AB","AB")+ "회 포함\n");
                System.out.println("총 " + count("01ABCB34ABC12ABC345ABC","ABC")+ "회 포함\n");
                System.out.println("총 " + count("12345","AB")+ "회 포함");


                System.out.println("");

                String a = "01234AB12AB345AB";
                System.out.println("\"01234AB12AB345AB\" 0번째 위치에서 부터 찾은 \"AB\"는 어디에 있는지? " + a.indexOf("AB",0) + "번째");
                System.out.println("\"01234AB12AB345AB\" 7번째 위치에서 부터 찾은 \"AB\"는 어디에 있는지? " + a.indexOf("AB",7) + "번째");

            }

        }

##### chapter9_4

첫번째 문자열(src)에 두번째 문자열(target)이 포함되어있는지 확인한다.
포함되어있으면 true, 불포함일 경우 false

indexof사용

- 결과

        true
        false
        <-- contains -->
        abcdefg에 "a" 가 포함되어있는지 : true

- 코드

        package pr9.pr9_4_contain;

        public class Pr9_4 {

            public static boolean con(String src, String target) {

                return src.indexOf(target)!=-1;
            }

            public static void main(String[] args) {
                System.out.println(con("12345","12"));
                System.out.println(con("12345","56"));

                String a = "abcdefg";
                System.out.println("<-- contains -->");
                System.out.println(a + "에 \"a\" 가 포함되어있는지 : " + a.contains("a"));

            }

        }
