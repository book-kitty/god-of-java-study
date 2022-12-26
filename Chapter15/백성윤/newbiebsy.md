# chapter15. String

#### 자바에서 가장 많이 사용하는 String 클래스
> String 클래스는 Serializable, Comparable<String>, CharSequence 인터페이스를 구현한다.   
> final 로 선언되어 있기 때문에 상속 불가능하다.

#### String의 생성자에는 이런 것들이 있다.
> 보통 String은 아래와 같이 간단하게 선언한다.
> ````
> String name = "Sangmin, Lee";
> ````
> 하지만 String의 생성자는 매우 많다. 각각의 생성자를 다 외울 필요는 없고 필요한 생성자를 API에서 찾아 사용하면 된다.   

#### 객체의 null 체크는 반드시 필요하답니다.
> String의 메소드를 사용하기 전에 반드시 널 체크를 해야 한다. (String뿐만 아니라 모든 객체 처리시)   
> null 은 객체가 아무런 초기화가 되어 있지 않으며, 해당 클래스에 어떤 메소드도 사용할 수 없다는 것을 의미한다.

#### String의 내용을 비교하고 검색하는 메소드들이 있어요
> String의 메소드들
> - 문자열의 길이를 확인하는 메소드
>   - length()
> - 문자열이 비어 있는지 확인하는 메소드
>   - isEmpty()
> - 문자열이 같은지 비교하는 메소드
>   - equals(), equalsIgnoreCase(), compareTo(), contentEquals()
> - 특정 조건에 맞는 문자열이 있는지를 확인하는 메소드
>   - startsWith(), endWith(), contains() 등등..

#### String의 값의 일부를 추출하기 위한 메소드들은 얘네들이다.
> 값을 추출하는 메소드의 종류는 다음과 같이 구분할 수 있다.
> - char 단위의 값을 추출하는 메소드
>   - charAt(), getChars(), codePointAt() 등등
> - char 배열의 값을 String으로 변환하는 메소드
>   - copyValueOf(), copyValueOf()
> - String의 값을 char 배열로 변환하는 메소드
>   - toCharArray()
> - 문자열의 일부 값을 잘라내는 메소드
>   - substring(), subSequence()
> - 문자열을 여러 개의 String 배열로 나누는 메소드
>   - split()

> 특정 형식에 맞춰 값을 치환하는 메소드
> - format()
>
> 기본 자료형을 문자열로 반환하는 메소드
> - valueOf()

#### 절대로 사용하면 안 되는 메소드가 하나 있어요! 
> intern() 메소드를 사용하여 억지로 String pool 에 값을 할당하면, 저장되는 영역은 한계가 있기 때문에 그 영역에 대해서 별도로 메모리를 청소하는 단계를 거치게 된다.    
> 작은 연산 하나를 빠르게 하기 위해서 전체 자바 시스템에 악영향을 주게 되는 것이다. 따라서 사용해서는 안된다.

### String의 단점을 보완하는 StringBuffer와 StringBuilder
> String 객체는 변하지 않는다. String 문자열을 더하면 새로운 String 객체가 생성되고 기존 객체는 버려진다.    
> 이러한 String 클래스의 단점을 보완하기 위해서 나온 클래스가 StringBuffer와 StringBuilder이다.    
> 두 클래스의 메소드는 동일하지만 StringBuffer는 Thread safe 하고 StringBuilder는 그렇지 않다.    
> *참고로 JDK 5 이상에서는 String 더하기 연산을 할 경우 컴파일할 때 자동으로 해당 연산을 StringBuffer로 변환해준다.(for 루프와 같이 반복 연산을 할 때에는 아니다.)*
