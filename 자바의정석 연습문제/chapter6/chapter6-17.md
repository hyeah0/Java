### chapter6-17

-코드

        package pr6_17;

        import java.util.Arrays;

        public class Pr6_17 {
            public  static int[] shuffle(int[] arr) {

                if(arr == null || arr.length ==0)
                    return arr;

                for(int i=0; i< arr.length;i++) {
                    int j = (int)(Math.random()*arr.length);
                    // arr[i]와 arr[j]의 값을 서로 바꾼다.

                    System.out.println("");
                    System.out.println("");

                    int tmp = arr[i];
                    System.out.println("==================1==================");
                    System.out.println("tmp = arr[i] ");
                    System.out.println("arr["+ i + "] : " + arr[i]);
                    System.out.println("tmp = " + tmp);

                    System.out.println("==================2==================");
                    arr[i] = arr[j];
                    System.out.println("arr[i] = arr[j] ");
                    System.out.println("arr["+ i + "] = arr["+ j + "]");
                    System.out.println("arr["+ j +"] : " + arr[j]);
                    System.out.println("arr["+ i + "] : " + arr[j]);

                    System.out.println("==================3==================");
                    arr[j] = tmp;
                    System.out.println("arr[j] = tmp ");
                    System.out.println("arr["+ j +"] = " + tmp);
                    System.out.println(Arrays.toString(arr));
                    System.out.println("=====================================");

                    }
                    return arr;
            }

                    public static void main(String[] args) {

                        int[] original = {1,2,3,4,5,6,7,8,9};
                        System.out.println("arr 오리지널");
                        System.out.println(java.util.Arrays.toString(original));

                        int[] result = shuffle(original);
                        System.out.println(java.util.Arrays.toString(result));

                    }

        }

- 결과

        arr 오리지널
        [1, 2, 3, 4, 5, 6, 7, 8, 9]

        ==================1==================
        tmp = arr[i]
        arr[0] : 1
        tmp = 1
        ==================2==================
        arr[i] = arr[j]
        arr[0] = arr[6]
        arr[6] : 7
        arr[0] : 7
        ==================3==================
        arr[j] = tmp
        arr[6] = 1
        [7, 2, 3, 4, 5, 6, 1, 8, 9]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[1] : 2
        tmp = 2
        ==================2==================
        arr[i] = arr[j]
        arr[1] = arr[8]
        arr[8] : 9
        arr[1] : 9
        ==================3==================
        arr[j] = tmp
        arr[8] = 2
        [7, 9, 3, 4, 5, 6, 1, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[2] : 3
        tmp = 3
        ==================2==================
        arr[i] = arr[j]
        arr[2] = arr[6]
        arr[6] : 1
        arr[2] : 1
        ==================3==================
        arr[j] = tmp
        arr[6] = 3
        [7, 9, 1, 4, 5, 6, 3, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[3] : 4
        tmp = 4
        ==================2==================
        arr[i] = arr[j]
        arr[3] = arr[6]
        arr[6] : 3
        arr[3] : 3
        ==================3==================
        arr[j] = tmp
        arr[6] = 4
        [7, 9, 1, 3, 5, 6, 4, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[4] : 5
        tmp = 5
        ==================2==================
        arr[i] = arr[j]
        arr[4] = arr[4]
        arr[4] : 5
        arr[4] : 5
        ==================3==================
        arr[j] = tmp
        arr[4] = 5
        [7, 9, 1, 3, 5, 6, 4, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[5] : 6
        tmp = 6
        ==================2==================
        arr[i] = arr[j]
        arr[5] = arr[2]
        arr[2] : 1
        arr[5] : 1
        ==================3==================
        arr[j] = tmp
        arr[2] = 6
        [7, 9, 6, 3, 5, 1, 4, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[6] : 4
        tmp = 4
        ==================2==================
        arr[i] = arr[j]
        arr[6] = arr[6]
        arr[6] : 4
        arr[6] : 4
        ==================3==================
        arr[j] = tmp
        arr[6] = 4
        [7, 9, 6, 3, 5, 1, 4, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[7] : 8
        tmp = 8
        ==================2==================
        arr[i] = arr[j]
        arr[7] = arr[1]
        arr[1] : 9
        arr[7] : 9
        ==================3==================
        arr[j] = tmp
        arr[1] = 8
        [7, 8, 6, 3, 5, 1, 4, 9, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[8] : 2
        tmp = 2
        ==================2==================
        arr[i] = arr[j]
        arr[8] = arr[4]
        arr[4] : 5
        arr[8] : 5
        ==================3==================
        arr[j] = tmp
        arr[4] = 2
        [7, 8, 6, 3, 2, 1, 4, 9, 5]
        =====================================
        [7, 8, 6, 3, 2, 1, 4, 9, 5]

- 결과 상세

        System.out.println("arr 오리지널");
        System.out.println(java.util.Arrays.toString(original));
        -->
        arr 오리지널
        [1, 2, 3, 4, 5, 6, 7, 8, 9]

        int[] result = shuffle(original);
        -->for문
        int tmp = arr[i];  1. tmp 값에 arr[0~] 값 지정
        arr[i] = arr[j];   2. -> arr[0]에 arr[랜덤값]값 지정
        arr[j] = tmp;      3. arr[랜덤] 값에는 tmp값 지정 (tmp : 배열순서대로 저장했던값)
                              = arr[0~] 값과 arr[랜덤] 값을 서로 바꿈
        
        
        ==================1==================
        1. tmp 값에 배열 순서대로 값 저장
        tmp = arr[i]
        arr[0] : 1
        tmp = 1
        -> tmp 값에 arr[0] 값 지정
        ==================2==================
        2. arr[0~] 배열값을 arr[랜덤] 랜덤 값으로 지정
        arr[i] = arr[j]
        arr[0] = arr[6]
        arr[6] : 7
        arr[0] : 7
        -> arr[0]에 arr[7]값 지정
        ==================3==================
        3. arr[랜덤] 값에는 tmp값 지정 (tmp : 배열순서대로 저장했던값)
        arr[j] = tmp
        arr[6] = 1
        [7, 2, 3, 4, 5, 6, 1, 8, 9]
        -> arr[0] 값과 arr[6] 값을 서로 바꿈
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[1] : 2
        tmp = 2
        ==================2==================
        arr[i] = arr[j]
        arr[1] = arr[8]
        arr[8] : 9
        arr[1] : 9
        ==================3==================
        arr[j] = tmp
        arr[8] = 2
        [7, 9, 3, 4, 5, 6, 1, 8, 2]
        =====================================


        ==================1==================
        tmp = arr[i]
        arr[2] : 3
        tmp = 3
        ==================2==================
        arr[i] = arr[j]
        arr[2] = arr[6]
        arr[6] : 1
        arr[2] : 1
        ==================3==================
        arr[j] = tmp
        arr[6] = 3
        [7, 9, 1, 4, 5, 6, 3, 8, 2]
        =====================================

        x 9 번 반복

        System.out.println(java.util.Arrays.toString(result));
        -->
        [7, 8, 6, 3, 2, 1, 4, 9, 5]
