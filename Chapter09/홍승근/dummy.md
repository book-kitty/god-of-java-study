## 패키지 이름의 기본적인 규칙
* java : 자바 기본 패키지(Java 벤더에서 개발)
* javax : 자바 확장 패키지(Java 벤더에서 개발)
* org : 일반적으로 비 영리단체(오픈 소스)의 패키지
* com : 일반적으로 영리단체(회사)의 패키지
> 그리고 이러한 자바 패키지의 이름을 지정할 때 유의점이 있다.
1. 패키지 이름은 모두 소문자로 지정해야 한다
  * 반드시는 아니지만 소문자로 사용하기로 약속이 되어 있다. 
2. 자바의 예악어를 사용하면 절대 안 된다.
  * 예를 들어 com.int.util과 같이 패키지 이름에 int와 같은 예악어는 포함되면 안 된다.
