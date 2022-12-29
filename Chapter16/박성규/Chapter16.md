# ❓16장 클래스 안에 클래스가 들어갈 수도 있구나
Nested 클래스에 속하는 3가지 클래스에는 어떤 것들이 있나요? 
static nested class, local inner class, anonymous inner class
Nested 클래스를 컴파일하면 Nested클래스 파일의 이름은앞에 $ 붙는다.
Static Nested 클래스는 다른 Nested 클래스와 인스턴스 없이 내부 클래스의 인스턴스를 바로 생성할 수 있다는 차이가 있다.
StaticNested 클래스의 객체 생성은 new Class.InnerClass 를 사용한다.
일반적인 내부 클래스의 객체 생성은 mc.new InnerClass()를 사용한다.
Nested 클래스를 만드는 이유는 코드를 간단하게 표현하기 위함이다.
Nested 클래스에서 감싸고 있는 클래스의 private 로 선언된 변수에 접근할 수 있나요? O
