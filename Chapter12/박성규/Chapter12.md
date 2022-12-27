# ❓12장 모든 클래스의 부모 클래스는 Object에요
   
## 부모클래스 Object
모든 클래스의 최상위 부모 클래스인 Object 클래스는 java.lang패키지에 설치되어 있다.<br>
클래스가 어떻게 선언되어 있는지 확인할 수 있는 명령어(실행파일)의 이름은 javap이다.<br>
Object 클래스에 선언되어 있는 모든 메소드를 Overriding할 필요 없다.<br>
Object 클래스의 clone() 메소드의 용도는 복제이다.<br>
System.out.println() 메소드를 사용하여 클래스를 출력했을 때 "최종적으로" 호출되는 Object 클래스에 있는 메소드는 toString이다.<br>
객체의 주소를 비교하는 것이 아닌, 값을 비교하려면 Object 클래스에 선언되어 있는 equals메서드를 overriding한다.
