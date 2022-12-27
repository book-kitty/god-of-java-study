# chapter12. 모든 클래스의 부모 클래스는 Object에요.

### java.lang.object 클래스
> 모든 자바 클래스의 부모 클래스는 Object 이다.   
> 자바는 다중 상속을 받을 수 없지만, 여러 단계로 상속을 받을 수는 있다.   

> 그러면 왜 모든 클래스는 Object 클래스의 상속을 받는가?   
> 이는 Object 클래스의 메소드들을 통해서 클래스의 기본적인 행동을 정의할 수 있기 때문이다.

### Object 클래스에서 제공하는 메소드들의 종류는 ? 
- protected Object clone()
  - 객체의 복사본을 만들어 리턴한다.
- public boolean equals(Object obj)
  - 현재 객체와 매개 변수로 받은 객체가 같은지 확인하여 true, false를 리턴한다.
- protected void finalize()
  - 현재 객체가 쓸모 없어졌을 때 GC에 의해서 호출된다.
- public Class<?> getClass()
  - 현재 객체의 클래스의 객체를 리턴한다.
- public int hashCode()
  - 객체에 대한 해시 코드 값을 리턴한다. (해시 코드 : 16진수로 제공되는 객체의 메모리 주소)
- public String toString()
  - 객체를 문자열로 표현하는 값을 리턴한다.   

... 등이 있다.
