### String 클래스 선언

- public final class String implements java.io.Serializable, Comparable<String>, CharSequence
    - Serializable : 구현해야 하는 메서드가 하나도 없는 인터페이스로, 해당 인터페이스를 구현한다고 선언해놓으면 해당 객체를 파일로 저장학더나 다른 서버에 전송 가능한 상태가 된다.
    - Comparable<String> : 해당 인터페이스는 compareTo() 메서드 하나만 선언되어 있으며, 해당 메서드는 매개 변수로 넘어가는 객체와 현재 객체가 같은지를 비교하는 데 사용한다.
    - CharSequence : 해당 인터페이스는 해당 클래스가 문자열을 다루기 위한 클래스라는 것을 명시적으로 나타내는데 사용된다. (StringBuilder, StringBuffer도 해당 인터페이스를 구현해놓았다. )
    

### 자바에서 한글

- EUC-KR
    - 한글 두 글자(4바이트)
- UTF-8,16
    - 한글 두 글자(6바이트)
    
    <img width="411" alt="Untitled (1)" src="https://user-images.githubusercontent.com/56379649/209822171-2530ec28-ff5b-4840-86ae-68a7a457fdc5.png">
    
    <img width="59" alt="Untitled (2)" src="https://user-images.githubusercontent.com/56379649/209822180-8eb7450a-2b19-4447-a948-8f5cc541153c.png">
    
    ### 객체가 null이다
    
    == 객체가 아무런 초기화가 되어 있지 않다. 
    
    == 클래스에 선언되어 있는 어떤 메서드도 사용할 수 없다. 
    
    == null 체크를 하지 않을 경우 객체에 사용할 수 있는 메서드들은 모두 예외를 발생시킨다. 
    
    ### 문자열 같은지 비교하는 메서드-IgnoreCase 포함 메서드는 대소문자 구분 X
    
    - equals(Object object);
    - equalsIgnoreCase(String anotherStr);
    - compareTo(String str);
    - compareToIgnoreCase(String str);
    - contentEquals(CharSequence cs);
    - contentEquals(StringBuffer sb);
    
    ---
    
    다음의 예시를 들어보자
    
    String a = "Java";
    String b = "Java";
    
    String c = new String("Java");
    
    만약 이 경우 (a == b) 참을 반환하나, 
    
    (a == c) 이 경우에는 거짓을 반환한다. 
    
    그 이유는 자바가 String을 2가지 방법으로 생성할 수 있기 때문이다. 
    
    첫 번째 경우 : 문자열을 그대로 할당하는 방식 (String literal)
    
    - 자바의 heap 영역에 있는 String Constant Pool에 문자열이 저장되어 재사용이 가능하다. 따라서 a,b는 String Constant Pool의 같은 곳을 가리키고 있어 둘은 같은 것으로 판단된다.
    
    두 번째 경우 : new 연산자를 사용하여 새로운 객체를 만들어 할당하는 방식
    
    - new 연산자를 사용할 시 Heap 영억에 새로운 객체가 만들어지기 때문에 다른 값으로 판단한다.
    
    그래서 다음의 경우 
    
    String a = new String("Java");
    String b = new String("Java");
    
    a == b          ⇒ Heap 영역에 따로 객체가 생성되어 다른 값으로 판단
    
    a.equals(b)    ⇒ 두 값의 내용물만 비교하기에 같은 값으로 판단
    
    ---
    
    ### 특정 조건에 맞는 문자열이 있는지 확인하는 메서드
    
    - startWith(String prefix);
    - startWith(String prefix, int toffset);
    - endWith(String sufix);
    - contains(CharSequence);
    - matches(String regex);
        - 매개 변수로 넘어오는 값이 졍규식으로 되어 있어야만 한다.
    - regionMatches(boolean ignoreCase, int toffset, String other, int ooffset, int len);
    - regionMatches(int toffset, String other, int ooffset, int len);
    
    ### String의 값 일부를 추출하기 위한 메서드
    
    - charAt(int index)
    - getChars(int srcBegin, int srcBegin, int srcEnd, char[] dst, int dstBegin)
    - codePointAt(int index)
    - codePointBefore(int index)
    - codePointCount(int beginIndex, int endIndex)
    - offsetByCodePoints(int index, int codePointOffset)
    
    ### Char 배열의 값을 String으로 변환하는 메서드
    
    - copyValueOf(char[] data)
    - copyValueOf(char[] data, int offset, int count)
    
    ### String값을 char 배열로 변환하는 메서드
    
    - toCharArray()
    
    ### 문자열의 일부 값을 잘라내는 메서드
    
    - subString(int beginIndex)
    - subString(int beginIndex, int endIndex)
    - subSequence(int beginIndex, int endIndex)
    
    ### 문자열을 여러 개의 String 배열로 나누는 메서드
    
    - split()
    
    ### 문자열을 합치는 메서드와 공백을 없애는 메서드
    
    - concat(String str)
    - trim()
    
    ### 내용을 교체하는 메서드
    
    - replace()
    - replaceAll()
    - replaceFirst()
    
    ### 특정 형식에 맞춰 값을 치환하는 메서드
    
    - format()
    
    ### 대소문자를 바꾸는 메서드
    
    - toLowerCase()
    - toUpperCase()
    
    ### 기본 자료형을 문자열로 변환하는 메서드
    
    - valueOf()
  
  ---
    
    ### String 클래스 내 절대로 사용하지 말아야 할 메서드
    
    - intern() 메서드의 경우 자바가 아닌, C로 구현되어 있는 메서드이다.
    - intern() 메서드가 호출될 경우 String Constant Pool에 있는 각종 문자열에 equals()해서 같은게 있다면 그것을 반환하고, 같은게 없을 시 String Constant Pool에 String Object를 추가하고 추가한 것을 반환한다.
    - 해당 메서드를 수행한 뒤 문자열은 equals()가 아닌 “==”으로 동일한지 비교한다.
    - 장점 : 처리 과정에서 Heap 메모리를 아낄 수 있다.
    - 단점
        - String 객체를 하나 만든 뒤 equals() 메서드를 이용해서 String Constant Pool에 있는 문자열을 찾아서 비교하는 과정에서 시간이 걸린다.
        - String Constant Pool에 들어갔으므로, 더 이상 GC의 대상이 될 수 없어 메모리 관리가 불가능하다.
        - 억지로 문자열 풀에 값을 할당하도록 만들면 저장되는 영역에는 한계가 있기 때문에 그 영역에 대해 별도로 메모리를 청소하는 단계를 거치게 되는데 그 과정에서 시스템 성능에 악영향을 준다.
    
    ### String은 immutable(불변)한 객체다.
    
    - String 문자열을 더하면 새로운 String 객체가 만들어지고 계속 더하는 작업을 할 시 더하기 이전에 초기화된 값들은 쓰레기가 되어 GC의 대상이 된다.
    - 이에 대한 단점을 보완하기 위해 StringBuffer와 StringBuilder가 나왔다.
        - 이 들은 더하는 과정에서 append()를 사용하는데, 이 때 새로운 객체를 생성하지 않는다.
    - **JDK 5 버전부터는 String의 더하기 연산을 할 경우 컴파일 시 자동으로 해당 연산을 StringBuilder로 변환해주지만, for 문과 같은 반복 연산 시 자동으로 변환해주지 않는다.**
    - StringBuffer
        - 동기화 키워드를 지원하여 멀티 쓰레드 환경에서 안전하다. (이건 String도 마찬가지)
        - 어떤 클래스에 문자열을 생성하여 더하기 위한 문자열을 처리하기 위한 인스턴스 변수가 선언되었고, 여러 쓰레드에서 이 변수를 동시에 접근하는 일이 있을 경우 사용
    - StringBuilder
        - 동기화 키워드를 지원하지 않으며, 단일쓰레드에서의 성능은 StringBuffer보다 뛰어나다.
        - 하나의 메서드 내에서 문자열을 생성하여 더할 경우 사용
    
  ---
  
    
    - String
        - 문자열 연산이 적고 멀티 쓰레드 환경일 경우 사용
    - StringBuffer
        - 문자열 연산이 많고 멀티 쓰레드 환경일 경우 사용
    - StringBulider
        - 문자열 연산이 많고 단일 쓰레드거나, 동기화를 고려하지 않아도 되는 경우 사용
