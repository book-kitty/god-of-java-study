> 정리

<br>

## 객체지향 관련 용어 목록

### 클래스

- 상태와 행위를 자바의 기본 단위를 의미한다.

### 상태와 행위

- 어떤 사물을 나타낼 때 상태와 행위로 구분하여 표시하는 것이 가능하며, 상태는 클래스나 인스턴스 변수로, 행위는 메서드로 표현한다.

### 캡슐화

- 연관된 상태와 행위를 결정하는 기능을 묶어주는 것을 의미한다.
- 기능을 클래스 밖에서 접근 가능한 대상을 제한하는 정보 은닉이 가능해진다.
- 하나의 객체를 위한 코드가 다른 객체를 위한 코드와 무관하게 수행할 수 있는 모듈화가 가능해진다.

### 메시지

- 메서드에서 다른 메서드를 호출할 때 전달하는 값을 메시지라고 한다.
- 자바에서는 메서드를 호출할 때 사용되는 매개 변수가 이에 해당된다.

### 객체

- 클래스는 사물의 단위를 의미하나, 객체는 각 사물 자체를 의미한다.

### 상속

- 부모에 선언된 변수와 메서드에 대한 사용권을 갖는 것을 말한다.
- 클래스 선언 시 extends, implements 가 그 예이다.

### 오버라이딩

- 부모 클래스에 선언되어 있는 메서드와 동일한 선언을 갖으나, 구현이 다른 것을 의미한다.

### 다형성

- 부모 클래스에서 파생된 자식 클래스들의 기능이 각기 다를 수 있음을 의미한다.

### 오버로딩

- 메서드의 이름은 동일해도 매개 변수들을 다르게 하는 것을 의미한다.
- 메서드에 넘겨줄 수 있는 매개 변수의 타입을 다양하게 함으로써 개발자가 쉽게 구현할 수 있게 해준다.

---

## 패키지와 import

- 패키지
    - 클래스들을 그룹화하기 위한 단위이다.
- import
    - 다른 패키지에 있는 클래스를 사용하기 위한 문장이다.

---

## 자바에서 사용되는 타입의 종류

- 자바의 타입은 크게 기본 자료형과 참조 자료형으로 나뉜다.

- 8개의 기본 자료형 : 숫자와 boolean을 나타내기 위한 자료형을 의미한다.
    - byte, short, int, long, char, float, double, boolean
- 참조 자료형 : 기본 자료형을 제외한 모든 타입을 의미하며 모든 클래스는 참조 자료형이다.
    - 참조 자료형과 기본 자료형의 차이
        - 초기화할 때
            - 기본 자료형은 바로 값을 지정하면 되지만, 참조 자료형은 일반적으로 new 와 생성자를 통해 객체를 생성한다.
        - 메서드를 호출할 때의 매개 변수
            - 기본 자료형과 참조 자료형은 모두 값을 전달하나, 참조 자료형 안에 있는 변수들은 참조 주소를 전달한다.
    - 특수한 참조 자료형
        - String : String 클래스는 new를 이용하여 객체를 생성할 필요가 없는 특수한 클래스로 + 연산까지 가능한 유일한 클래스이다.

---

## 변수의 종류

- 지역 변수
    - 선언된 스코프를 벗어나면 소멸된다.
- 매개 변수
    - 메서드를 호출할 때 생명이 시작되고 메서드가 끝나면 생명이 소멸된다.
- 인스턴스 변수
    - 객체를 생성 시 생명이 시작되고 그 객체를 참조하고 있는 다른 객체가 없으면 소멸된다.
- 클래스 변수
    - 클래스 생성 시 생명이 시작되고 자바 프로그램이 끝날 때 소멸된다.

---

## 접근 제어자

- public : 어디에서나 접근 가능
- protected : 같은 패키지 내 or 상속받은 경우 접근 가능
- default : 같은 패키지 내 접근 가능
- private : 해당 클래스 내 접근 가능

---

## 자바에서 만든 코드를 관리하는 클래스 파일 종류

- 클래스
    - 메서드가 구현되어 있어야 한다.
- 인터페이스
    - 어떤 메서드가 존재해야 하는지에 대한 선언만 되어 있다.
    - 절대로 구현되어 있는 메서드는 존재해선 안된다.
    - implement를 사용
- 추상 클래스
    - 구현되어 있는 메서드가 있어도 상관없다.
    - 추상 메서드 존재 시 추상 클래스로 선언해야만 한다.
    - 추상 메서드는 구현되어 있어선 안된다.
    - extends를 사용
- enum 클래스
    - 상수를 열거하기 위해 사용된다.
    - 모든 enum 클래스의 부모는 java.lang.Enum 클래스 뿐이다.
    - enum에 메서드를 만들어 기능 추가 가능
- 어노테이션 선언 클래스
    - 대상(@Target)과 적용 범위(@Retention)를 명시하는 것이 좋다.
    - @interface를 사용하여 어노테이션임을 명시한다.

---

## String 클래스

- String 클래스의 경우 더하기 연산 시 기존 문자열은 버리고 새로운 객체를 생성한다.
