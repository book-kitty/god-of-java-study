> 정리
> 

### 모든 클래스에는 부모 클래스가 존재한다.

- 자바에서는 기본적으로 아무런 상속을 받지 않으면, java.lang.Object 클래스를 확장한다.
    - 그 이유는 Object 클래스에 있는 메서드들을 통해 클래스의 기본적인 행동을 정의할 수 있기 때문이다.
- Object 클래스에 선언되어 있는 메서드는 둘로 나뉜다.
    - 객체를 처리하기 위한 메서드
        - clone(), equals(), finalize(), getClass(), hashCode(), toString() 등이 있다.
    - 쓰레드를 위한 메서드
        - notify(), notifyAll(), wait() 등이 있다.
    
- ==, != : 주소값을 비교한다.
- equals() : 데이터를 비교한다.

### 객체는 “==” 만으로 같은지 확인이 안되므로 equals()를 사용한다.

- equals() 오버라이딩의 정석

```
package com.yang.app;

public class Test {

    public String name;
    public String phone;
    public String email;

    public boolean equals(Object obj) {

        if (this == obj) return true;   // 주소가 같으므로 true
        if (obj == null) return false;  // obj가 null이므로 false
        if (getClass() != obj.getClass()) return false; // 클래스의 종류가 다르므로 false
        Test other = (Test) obj;        // 같은 클래스이므로 형 변환 실행

        // 이제부터는 각 인스턴스 변수가 같은지 비교하는 작업 수행

        if (name == null) { // name이 null인 경우
            if (other.name != null) return false;   // 비교 대상의 name이 null이 아니면 false
        } else if (!name.equals(other.name)) return false; // 두 개의 email 값이 다르면 false

        // name와 같은 비교 수행
        if (email == null) {
            if (other.email != null) return false;
        } else if (!email.equals(other.email)) return false;

        if (phone == null) {
            if (other.phone != null) return false;
        } else if (!phone.equals(other.phone)) return false;

        // 위 조건 통과 시 true
        return true;
    }
}

```

- 참고로 equals() 오버라이딩 시 hashCode()도 오버라이딩 해야 한다.
    - equals() 를 통해 객체가 서로 같다고 할 순 있으나, 각 주소값은 다르기 때문이다.

위  두 메서드를 오버라이딩을 하는 행위는, 그 과정에서 제약 조건들이 존재하기에, 
보통 권장하지는 않는다.
