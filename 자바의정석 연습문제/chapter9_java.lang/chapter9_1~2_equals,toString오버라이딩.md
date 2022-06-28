### 연습문제

#### chapter9_1~2 equals(), toString() 오버라이딩

##### chapter9_1

sutdacard클래스의 equals()를 멤버변수인 num, isKwang의 값을 비교하도록 오버라이딩

- 결과

        1K
        s1 : 3K
        s2 : 3K
        s1.equals(s2) : true

- 코드

        package pr9.pr9_1_sutdaCard;

        class SutdaCard{
            int num;
            boolean isKwang;

            SutdaCard(){
                this(1,true);
            }

            SutdaCard(int i, boolean tf){
                this.num = i;
                this.isKwang = tf;
            }

            public boolean equals(Object obj) {
        //		매개변수로 넘겨진 객체의 i,tf 과 멤버변수 num,isKwang을 비교하도록 오버라이딩 하시오

                if(obj instanceof SutdaCard) {
                    SutdaCard s = (SutdaCard) obj;
                    return this.num == s.num && isKwang == s.isKwang;
                }
                return false;
            }

            @Override
            public String toString() {
                return num + (isKwang? "K" : "");
            }

        }

        public class Pr9_1 {

            public static void main(String[] args) {
                SutdaCard s = new SutdaCard();
                System.out.println(s.toString());


                SutdaCard s1 = new SutdaCard(3,true);
                SutdaCard s2 = new SutdaCard(3,true);

                System.out.println("s1 : " + s1);
                System.out.println("s2 : " + s2);
                System.out.println("s1.equals(s2) : " + s1.equals(s2));
            }

        }

##### chapter9_2

equals()를 멤버변수인 x,y,z의 값을 비교하도록 오버라이딩

- 결과

        [1,2,3]

        [2,3,4]
        [2,3,4]
        p1 == p2 : false
        p1.equals(p2)) : true

- 코드

        package pr9.pr9_2_print3D;

        class Point3D{
            int x,y,z;

            Point3D(){
                this(0,0,0);
            }

            Point3D(int a, int b, int c){
                this.x = a;
                this.y = b;
                this.z = c;
            }

            public boolean equals(Object obj) {
                if(!(obj instanceof Point3D)) return false;
                Point3D p = (Point3D) obj;
                return this.x == p.x && this.y == p.y && this.z == p.z;
            }

            @Override
            public String toString() {
                return "[" + x + "," + y + "," + z +"]";
            }

        }

        public class Pr9_2 {
            public static void main(String[] args) {
                Point3D p = new Point3D(1,2,3);
                System.out.println(p.toString());
                System.out.println("");

                Point3D p1 = new Point3D(2,3,4);
                Point3D p2 = new Point3D(2,3,4);
                System.out.println(p1.toString());
                System.out.println(p2.toString());
                System.out.println("p1 == p2 : " + (p1 == p2));
                System.out.println("p1.equals(p2)) : " + (p1.equals(p2)));

            }
        }
