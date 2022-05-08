## 자바의 정석 chapter 5 배열

### 1. 배열이란?

같은 타입의 여러변수를 하나의 묶음으로 다루는것

### 2. 배열의 선언과 생성

##### 배열 선언

- 타입[] 변수이름;

  예시)
  int[] score;
  String[] naem;

- 타입 변수이름[];

        예시)
        int score[];
        String name[];

##### 배열 생성

- 타입[] 변수이름;
  변수이름 = new 타입[길이];

              예시)
              int[] score;
              score = new int[5];

- 타입[] 변수이름 = new 타입[길이]

            예시)
            int[] score = new int[5]
            배열선언과 동시에 길이가 5인 int 배열

### 3. 배열의 인덱스

인덱스의 범위는 0부터 "배열길이의 -1" 까지

### 4. 배열의 길이

배열이름.length

        예시)
        int[] arr = new int[6];
        int tmp = arr.length;

        --> arr = int 값이 6개 있는 배열이고 인덱스는 0~5까지 있다
        --> tmp = arr의 길이는 6이다.

\* 배열 + for 문 사용시 \*

        int[] score = new int[5];
        for(int i=0; i<score.length; i++)
            System.out.println(score[i]);

### 5. 배열의 초기화

배열 생성과 동시에 자동적으로 기본값(0)으로 초기화 된다.
원하는 값을 저장하려면 아래와 같이 값을 지정해야한다.

        int[] score = new int[]{10,20,30,40,50};
        또는 int[] score = {10,20,30,40,50};

        new int[] 생략 가능

### 6. 배열의 출력

배열을 출력시에 for문을 사용하면 된다.
만약 배열을 바로 출력시 타입@주소 형식으로 출력된다

        int[] score = {10,20,30,40,50};
        System.out.print(score); --> [I@aec6354
        for(int i=0; i<score.length; i++)
            System.out.print(score[i]); --> 1020304050

        System.out.println(Arrays.toString(num));

        Arrays.toString 사용시
        import java.util.Arrays; 작성 필요

예외) 문자(char)는 바로 출력된다.

        char[] chArr = {'a','b','c'};
    	System.out.println(chArr);	--> abc

    	String[] stArr = {"사과","오렌지","포도","키위"};
    	System.out.println(stArr); -->[Ljava.lang.String;@1c655221
