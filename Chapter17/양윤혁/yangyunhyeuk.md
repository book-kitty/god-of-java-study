> 정리

<br>

### 어노테이션

- 컴파일러에게 정보를 알려줄 때 사용한다.
- 컴파일 할 때 설치 시 작업을 지정하거나 실행 할 때 별도의 처리가 필요할 때 사용한다.

### 자바에서 일반적으로 사용 가능한 어노테이션은 다음의 3개이다.

- @Overide
    - 부모 클래스에 있는 메서드를 Overide한 경우
- @Deprecated
    - 이미 만들어둔 클래스, 메서드를 더 이상 사용하지 않는  경우
- @SuperWarnings
    - 프로그램에는 문제가 없어, 경고를 제외시켜야 하는 경우
    

### 메타 어노테이션 (선언을 하기 위한 어노테이션)

- @Target
    - 어노테이션을 어떤 것에 적용할지를 선언할 때 사용한다.
        - @Target(ElementType.METHOD)
        - 이외에도 괄호 내 CONSTRUCTOR, FIELD, LOCAL_VARIABLE, METHOD, PACKAGE, PARAMETER, TYPE 등을 사용할 수 있다.
- @Retention
    - 얼마나 오래 어노테이션 정보가 유지되어야 하는지를 선언할 때 사용한다.
        - @Retention(RetentionPolicy.RUNTIME)
            - 이외에도 괄호 내 SOURCE, CLASS, RUNTIME이 있다.
- @Documented
    - 해당 “어노테이션에 대한 정보가 Javadocs(API) 문서에 포함된다는 것”을 선언한다.
- @Inherited
    - 모든 자식 클래스에서 부모 클래스의 어노테이션을 사용 가능하다는 것을 선언한다.

- 미리 만들어놓은 어노테이션은 확장이 불가능하다. 즉, extends 예약어를 사용할 수 없다.
- 어노테이션은 용도에 따라 다음과 같이 나눌 수 있다.
    - 제약사항 등을 선언하기 위해
        - @Deprecated, @Overide, @NotNull
    - 용도를 나타내기 위해
        - @Empty, @TestCase, @WebService
    - 행위를 나타내기 위해
        - @Statefull, @Transaction
    - 처리를 나타내기 위해
        - @Coulumn, @XmlElement
- 어노테이션이 만들어지면서 각 설정이 필요한 위치에 관련 설정이 존재하면서 
코드에 대한 가독성이 매우 좋아졌으며, 단순 반복적인 작업도 줄이는 데 도움을 준다.
