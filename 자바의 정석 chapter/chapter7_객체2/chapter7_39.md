#### cp7_39 인터페이스의 장점

1. 개발시간 단축
2. 표준화 가능
3. 서로 관게없는 클래스들에게 관계를 맺어 줄 수 있다.
4. 독립적인 프로그래밍 가능

   - 인터페이스를 이용하여 클래스의 선언과 구현을 분리시킬 수 있다.

#### 4. 예시

##### case 1. 인터페이스를 사용을 안했을때

- 의존하고 있는 클래스에 따라 변경 필요 (A 클래스 메서드 변경 필요)

       package cp7.ex7_39;

       class A{
           public void method(C c) { // 의존하고 있는 클래스에 따라 변경 필요
               c.method();
           }
       }
       class B{
           public void method() {
               System.out.println("B클래스의 메서드");
           }
       }
       class C{
           public void method() {
               System.out.println("C클래스의 메서드");
           }
       }

       public class Ex7_39 {

           public static void main(String[] args) {

               A a = new A();
       //		a.method(new B()); //a 가 b를 사용(a가 b를 의존하고 있음)

               A a2 = new A();
               a2.method(new C()); //a 가 c를 사용(a가 c를 의존하고 있음)
           }

       }

- 결과

        C클래스의 메서드

##### case 2. 인터페이스를 사용 했을때

- 의존하고 있는 클래스에 따라 변경 필요없다.

        package cp7.ex7_39;

        class D{
            public void method(Method m) { // 의존하고 있는 클래스에 따라 변경 필요 x
                m.method();
            }
        }

        // 인터페이스 생성으로 선언과 구현을 분리
        interface Method{
            public void method() ;
        }

        class E implements Method{
            public void method() {
                System.out.println("E클래스의 메서드");
            }
        }
        class F implements Method{
            public void method() {
                System.out.println("F클래스의 메서드");
            }
        }

        public class Ex7_39_2 {

            public static void main(String[] args) {
                D d = new D();
                d.method(new E()); //d 가 e를 사용(d가 e를 의존하고 있음)
                d.method(new F()); //d 가 f를 사용(d가 f를 의존하고 있음)

            }
        }

- 결과

        E클래스의 메서드
        F클래스의 메서드
