#### cp7_38 인터페이스를 이용한 다형성

- 추상 클래스 상속, 인터페이스 구현
- 다형성 : 참조변수(조상) = new 자손

#### 예시

        package cp7.ex7_38;

        abstract class Unit{
            int x, y;
            abstract void move(int x, int y);
            void stop() {System.out.println("멈춥니다.");}
        }

        interface Fightable{
            public abstract void move(int x, int y); //public abstract 생략가능
            public abstract void attack(Fightable f); //public abstract 생략가능
        }

        class Fighter extends Unit implements Fightable{ //Unit 추상클래스 상속, Fightable 인터페이스 구
            // 오버라이딩 : 상속받은 메서드 수정
            // 오버라이딩 : 조상(public) 보다 접근제어자 범위가 좁으면 안된다.

            public void move(int x, int y) {
                System.out.println("[ "+ x +" , " + y + " ] 로 이동" );
            }
            public void attack(Fightable f) {
                System.out.println( f + "를 공격");
            }

            // 싸울 수 있는 상대를 불러온다.
            Fightable getFightable() { // 반환타입 : Fightable
                Fightable f = (Fightable) new Fighter(); //Fightable를 생성해서 반환
                return f;
            }
        }

        public class Ex7_38 {

            public static void main(String[] args) {

                    // 자손
                    System.out.println("==자손==");
                    Fighter f = new Fighter();
                    f.move(1, 2);
                    f.attack(f);
                    System.out.println("f.toString() : " + f.toString());
                    f.stop();
                    Fightable f0 = f.getFightable(); // 싸울수 있는 상대를 불러오는 메서드와 반환타입을 맞춰야한다.
                    System.out.println("f0.toString() : " + f0.toString());
                    f.attack(f0);

                    System.out.println("");

                    f.attack(new Fighter());
                    // f.attack(new Fighter()); 식을 풀어쓴게 하단이다.
                    Fighter f2 = new Fighter();
                    f.attack(f2);

                    //추상클래스(조상) = new 자손
                    System.out.println("");
                    System.out.println("==추상클래스==");

                    Unit u = new Fighter();
                    u.move(120, 220);
        //			u.attack(u); // unit 추상클래스에는 attack 메서드가 없어 사용 불가
                    System.out.println("u.toString() : " + u.toString());
                    u.stop();

                    //인스턴스(조상) = new 자손
                    System.out.println("");
                    System.out.println("==인스턴스==");

                    Fightable fa = new Fighter();
                    fa.move(300, 320);
                    fa.attack(fa);
                    System.out.println("fa.toString() : " + fa.toString());
        //			fa.stop(); // Fightable 인스턴스에는 stop메서드가 없어 사용 불가

                    System.out.println("");

                    fa.attack(new Fighter());
                    // f.attack(new Fighter()); 식을 풀어쓴게 하단이다.
                    Fightable f3 = new Fighter();
                    f3.attack(f3);

            }

        }

#### 예시 상세

        package cp7.ex7_38;

- 추상 클래스

            abstract class Unit{
                int x, y;
                abstract void move(int x, int y);
                void stop() {System.out.println("멈춥니다.");}
            }

- 인터페이스

  - 모든 멤버변수는 public static final 이어야한다 (상수여야한다.)
  - 모든 메서드는 public abstract 이어야한다 ( 접근제어자는 public이어야하고 추상 메서드여야 한다.)

          interface Fightable{
              public abstract void move(int x, int y); //public abstract 생략가능
              public abstract void attack(Fightable f); //public abstract 생략가능
          }

- 추상클래스 상속받고, 인터페이스를 구현한 자손 클래스

  - 오버라이딩 : 상속받은 메서드 수정
    조상(public) 보다 접근제어자 범위가 좁으면 안된다.

          class Fighter extends Unit implements Fightable{

              // 인터페이스 메서드 완성
              public void move(int x, int y) {
                  System.out.println("[ "+ x +" , " + y + " ] 로 이동" );
              }
              public void attack(Fightable f) {
                  System.out.println( f + "를 공격");
              }

              // 싸울 수 있는 상대를 불러온다.
              Fightable getFightable() { // 반환타입 : Fightable
                  Fightable f = (Fightable) new Fighter(); //Fightable를 생성해서 반환
                  return f;
              }
          }

- 실행클래스

          public class Ex7_38 {

              public static void main(String[] args) {

- 객체생성 ( 자손 = new 자손 ) \_ 자손을 참조변수

                      System.out.println("==자손==");
                      Fighter f = new Fighter();
                      f.move(1, 2);
                      f.attack(f);
                      System.out.println("f.toString() : " + f.toString());
                      f.stop();

                      // 싸울수 있는 상대를 불러오는 메서드와 반환타입을 맞춰야한다.
                      Fightable f0 = f.getFightable();
                      System.out.println("f0.toString() : " + f0.toString());
                      f.attack(f0);

                      System.out.println("");

                      f.attack(new Fighter());
                      // =
                      Fighter f2 = new Fighter();
                      f.attack(f2);

- 객체생성 ( 추상클래스 = new 자손 ) \_ 조상(추상클래스)을 참조변수로

  - 추상클래스에 있는 메서드만 사용 가능

                    System.out.println("");
                    System.out.println("==추상클래스==");

                    Unit u = new Fighter();
                    u.move(120, 220);
                    System.out.println("u.toString() : " + u.toString());
                    u.stop();
                    // u.attack(u); // unit 추상클래스에는 attack 메서드가 없어 사용 불가

- 객체생성 ( 인스턴스 = new 자손 ) \_ 조상(인스턴스)을 참조변수로

  - 인스턴스에 있는 메서드만 사용 가능

                      System.out.println("");
                      System.out.println("==인스턴스==");

                      Fightable fa = new Fighter();
                      fa.move(300, 320);
                      fa.attack(fa);
                      System.out.println("fa.toString() : " + fa.toString());
             		  // fa.stop(); // Fightable 인스턴스에는 stop메서드가 없어 사용 불가

                      System.out.println("");

                      fa.attack(new Fighter());
                      // =
                      Fightable f3 = new Fighter();
                      f3.attack(f3);

              }

          }

#### 결과

            ==자손==
            [ 1 , 2 ] 로 이동
            cp7.ex7_38.Fighter@1b701da1를 공격
            f.toString() : cp7.ex7_38.Fighter@1b701da1
            멈춥니다.
            f0.toString() : cp7.ex7_38.Fighter@726f3b58
            cp7.ex7_38.Fighter@726f3b58를 공격

            cp7.ex7_38.Fighter@442d9b6e를 공격
            cp7.ex7_38.Fighter@ee7d9f1를 공격

            ==추상클래스==
            [ 120 , 220 ] 로 이동
            u.toString() : cp7.ex7_38.Fighter@15615099
            멈춥니다.

            ==인스턴스==
            [ 300 , 320 ] 로 이동
            cp7.ex7_38.Fighter@1edf1c96를 공격
            fa.toString() : cp7.ex7_38.Fighter@1edf1c96

            cp7.ex7_38.Fighter@368102c8를 공격
            cp7.ex7_38.Fighter@6996db8를 공격
