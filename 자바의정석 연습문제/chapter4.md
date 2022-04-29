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
        str.charAt(1) = 2 <- "12345" 에서 idx 0 번 문자
        str.charAt(2) = 3 <- "12345" 에서 idx 0 번 문자
        str.charAt(3) = 4 <- "12345" 에서 idx 0 번 문자
        str.charAt(4) = 5 <- "12345" 에서 idx 0 번 문자

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
