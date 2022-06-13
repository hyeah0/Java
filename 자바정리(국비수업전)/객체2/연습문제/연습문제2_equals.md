#### 연습문제

- 하단과 동일한 결과가 나오도록 코드 작성

        성별과 혈역형이 일치하는 인원이 있는 경우는 총 2가지

- Member 클래스에 equals를 오버라이딩(나이와 혈액형이 같으면 true가 나오도록) 객체의 정보를 반환하도록 toString을 오버라이딩

- Member class

        String name
        int age
        char gender
        char bloodt

- Run class

        Meber[] m 객체선언하고 5명의 객체생성
        m[0] : "김선후", 17, '남', 'B'
        m[1] : "홍미라", 34, '여', 'O'
        m[2] : "장수연", 20, '여', 'A'
        m[3] : "김가람", 27, '남', 'B'
        m[4] : "박수연", 25, '여', 'O'

##### 코드

###### Member class

       package p4.equals;

        public class Member {

            String name;
            int age;
            char gender;
            char bloodT;

            Member(){

            }

            Member(String name, int age, char gender, char bloodT){
                this.name = name;
                this.age = age;
                this.gender = gender;
                this.bloodT = bloodT;
            }

            public void member() {
                System.out.println("name : " + name +", age : "+ age + ", gender : " + gender +", blood type : " + bloodT);
            }

            @Override
            public boolean equals(Object obj) {
                Member m = (Member) obj;
                if(gender == m.gender && bloodT == m.bloodT)
                    return true;
                return false;

            }
        }

###### Run class

        package p4.equals;

        import java.util.Arrays;

        public class Run {

            public static void main(String[] args) {

        //		Member m = new Member("김선후", 17, '남', 'B');
        //		m.member();

                Member[] m = { new Member( "김선후", 17, '남', 'B' ),
                                new Member( "홍미라", 34, '여', 'O' ),
                                new Member( "장수연", 20, '여', 'A' ),
                                new Member( "김가람", 27, '남', 'B' ),
                                new Member( "박수연", 25, '여', 'O' )};

                Member[] tempM = new Member[8];
                for(int i=0; i<tempM.length; i++) {
                    tempM[i] = new Member();
                }

                int tempIndex = 0 ;
                for(int i =0; i<m.length; i++) { //기준이 되는 인원
                    for(int j=i+1; j<m.length; j++) { //비교가 되는 인원 (기존이되는 인원 리스트에 다음리스트)

                        if(m[i].equals(m[j])) {
                            int k;
                            for(k =0; k<tempM.length; k++) { //tempM 객체배열을 돌려가며 확인
                                if(m[j].equals(tempM[k])) {
                                    break;
                                }
                            }
                                if(k==tempM.length) {
                                    tempM[tempIndex++] = m[j];
                                }
                            }
                        }
                    }


                System.out.println("성별과 혈액형이 일치하는 인원이 있는 경우는 총 " + tempIndex + "가지 이다.");


            }

        }

###### 결과값

        성별과 혈액형이 일치하는 인원이 있는 경우는 총 2가지 이다.
