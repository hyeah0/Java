### chapter6-18

- 코드

        package pr6.pr6_18;

        import java.util.Scanner;

        class Pr6_18 {

            public static boolean isNumber(String str) {

                if(str ==null || str.equals(""))
                    return false;

                for(int i=0; i<str.length(); i++) {
                    char ch = str.charAt(i);

                    if(ch<'0'||ch>'9') {
                        return false;
                    }
                }
                return true;
            }

            public static void main(String[] args) {
                Scanner sc = new Scanner(System.in);
                String str = sc.nextLine();
                System.out.println(str + "는 숫자입니까?" + isNumber(str));

                str = "123";
                System.out.println(str + "는 숫자입니까?" + isNumber(str));

                str = "1234o";
                System.out.println(str + "는 숫자입니까?" + isNumber(str));
            }

        }

- 결과

        입력값
        입력값는 숫자입니까?ture/false
        123는 숫자입니까?true
        1234o는 숫자입니까?false
