### 연습문제

#### chapter9_5 주어진 문자열에서 문자 제거

> StringBuffer class -> append : 추가
> String class -> charAt(0) : 0번째 문자
> String class -> indexOf("a") : "a" 문자의 index ()가로안 문자가 없을경우 -1 반환

> > tmp = aaa.indexOf(target.charAt(j));
> > String 에서는 indexOf(char 또는 string) 사용 가능
> > StringBuffer에서는 indexOf(string)만 가능

- 결과

        ---------문제답---------
        (1!2@3^4~5) -> 12345
        (1 2 3 4	5) -> (12345)
        ---------추가---------
        s.deleteCharAt(1) : ab@c#d$e%f^g
        s.indexOf("@") : 2
        s.charAt(0)) : a

        abc#d$e%f^g
        abcd$e%f^g
        abcde%f^g
        abcdef^g
        abcdefg
        abcdefg

- 코드

        package pr9.pr9_5_delchar;

        public class Pr9_5 {

            public static String delChar(String src, String delCh) {

                StringBuffer sb = new StringBuffer(src.length());

                for(int i=0; i<src.length(); i++) {
                    char ch = src.charAt(i);
                    if(delCh.indexOf(ch) == -1)
                        sb.append(ch);
                }

                return sb.toString();
            }

            public static void main(String[] args) {
                System.out.println("---------문제답---------");
                System.out.println("(1!2@3^4~5)"+" -> " + delChar("(1!2@3^4~5)","~!@#$%^&*()"));
                System.out.println("(1 2 3 4\t5)"+" -> " + delChar("(1 2 3 4\t5)"," \t"));


                System.out.println("---------추가---------");
                String aaa = "a!b@c#d$e%f^g";
                String target = "!@#$%^&";
                StringBuffer s =  new StringBuffer("a!b@c#d$e%f^g");

                System.out.println("s.deleteCharAt(1) : " + s.deleteCharAt(1));  // ab@c#d$e%f^g
                System.out.println("s.indexOf(\"@\") : " + s.indexOf("@")); // 2
                System.out.println("s.charAt(0)) : " + s.charAt(0));  // a
                System.out.println("");


                int tmp = 0;
                for(int i=0; i<s.length(); i++) {
                    for(int j=0; j<target.length(); j++) {
                        tmp = s.indexOf(target.valueOf(target.charAt(j)));
                        if(tmp != -1) {
                            System.out.println(s.deleteCharAt(tmp));
                        }
                    }
                }

                System.out.println(s.toString());

            }
        }
