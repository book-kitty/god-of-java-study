# ❓14장 String
   
## String에 대해 알아봐요
String 클래스는  더 이상 이 클래스를 확장 할 수 없게 하기 위해서 final 클래스이다.<br>
String 클래스가 구현한 인터페이스에는 Serializable, Comparable, CharSequence가 있다.<br>
String 클래스의 생성자 중에서 가장 의미없는 (사용할 필요가 없는) 생성자는 기본 생성자이다.<br>
String 문자열을 byte 배열로 만드는 메소드의 이름은 getBytes()이다.<br>
String 문자열의 길이를 알아내는 메소드는 length()이다.<br>
String 클래스의 equals() 메소드와 compareTo() 메소드의 공통점은 객체의 주소값이 아닌 값만 가지고 비교한다는 것이고 리턴값은 다르다 equals() 는 boolean compareto()는 같을떈 0 다를땐 문자들의 차이의 값<br>
문자열이 "서울시"로 시작하는지를 확인하려면 String의 startsWith()를 사용해야 한다.<br>
