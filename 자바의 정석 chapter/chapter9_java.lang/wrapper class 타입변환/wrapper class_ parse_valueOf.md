### Wrapper class

8개의 기본 타입에 해당하는 데이터를 객체로 표현하기 위해, 포장해 주는 클래스

> 기본타입 : byte, short, char, int, long, float, double, boolean
> 참조 타입 : class, interface ..

java.lang package> object class > number class > Wrapper class

int -> integer : 오토박싱
int <- integer : 언박싱

                Integer num = new Integer(17); // Boxing
                int n = num.intValue(); // UnBoxing

                Character ch = 'X'; // AutoBoxing : Character ch = new Character('X');
                char c = ch; // AutoUnBoxing : char c = ch.charValue();

- 래퍼클래스는 모두 equals()가 오버라이딩 되어있어 주소값이 아닌 객체가 가지고 있는 값을 비교한다.

                Integer i = new Integer(100);
                Integer i2 = new Interger(100);

                i == i2 => false
                i.equals(i2) = true

### 문자열-> 기본형 또는 래퍼클래스

        byte b = Byte.parseByte("100"); 또는 Byte.valueOf("100");
        short s = Short.parseShort("100"); 또는 Short.valueOf("100");
        int i = Integer.parseInt("100"); 또는 Integer.valueOf("100");
        long l = Long.parseLong("100"); 또는 Long.valueOf("100");
        float f = Float.parseFloat("3.14"); 또는 Float.valueOf("3.14");
        double d = Double.parseDouble("3.14"); 또는 Double.valueOf("3.14);
