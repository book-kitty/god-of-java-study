

## 마주할 수 있는 예외 상황

- null인 객체에 메서드를 호출하는 경우
- 5개의 공간을 갖는 배열에 6번째 값을 요구하는 경우
- 어떤 파일을 읽으라고 명령했으나, 존재하지 않는 파일인 경우
- 네트워크 연결이 되어 있는 서버가 작동을 멈춰 연결이 끊기는 경우

## try-catch 내 예외가 발생한 경우

- try 내 예외가 발생한 경우 이후의 문장들은 수행되지 않는다.
- catch 내에 있는 문장은 반드시 실행되고, try-catch 문장 이후 내용이 실행된다.

## try-catch 내 예외가 발생하지 않은 경우

- try 내에 존재하는 모든 문장이 실행되고 try-catch 문장 이후의 내용이 실행된다.

- try절 이후에 오는 catch문은 1개 이상 존재할 수 있다.
- catch 블록 중 발생한 예외와 관련있는 블록이 없을 경우 예외가 발생되면서 해당 쓰레드는 끝이 난다. 따라서 마지막 catch 블록에는 Exception 클래스로 묶어주는 버릇을 들여놓아야 안전성을 보장할 수 있다.

## 자바에 존재하는 세 종류의 에러

### checked exception

### error

- 서버의 디스크가 고장났거나 메인보드가 장애일 경우에 발생하곤 한다.
- Exception 클래스는 에러가 아니라 예외이다. (오류의 이름이 Error로 끝나면 에러고, Exception일 경우 예외다.)
- Error와 Exception의 차이
    - Error
        - 프로세스에 영향을 주어 프로그램이 멈춘다.
    - Exception
        - 쓰레드에 영향을 주어 프로그램은 계속 실행 가능하다.

### runtime exception (unchecked exception)

- 예외가 발생할 것을 미리 감지하지 못했을 때 발생한다.
- 컴파일 시에 체크를 하지 않기 때문에 unchecked exception 라고도 부른다

### 예외 클래스 상관 관계도

![Untitled](https://user-images.githubusercontent.com/56379649/209821745-07cbbb36-15e1-42a3-935d-3e545841db93.png)

### 모든 예외의 할아버지는 java.lang.Throwable 클래스이다.

- Exception과 Error의 공통 부모 클래스는 당연히 Object 클래스이다. 
그리고 공통 부모 클래스가 또 하나 있는데, 바로 java.lang 패키지 내 Throwable 클래스이다. 
다시 말해, Exception이나 Error 클래스는 Throwable 클래스를 상속받아 처리하도록 되어 있다.
    - 상속관계가 이렇게 정의되어 있는 이유는 Exception, Error 성격은 다르나, 모두 동일한 이름의 메서드를 사용하여 처리할 수 있도록 하기 위함이다.
- Throwable 생성자는 다음과 같다.
    - Throwable()
    - Throwable(String message)
    - Throwable(String message, Throwable cause) // Throwable cause == 예외의 원인
    - Throwable(Throwable cause)
- Throwable 클래스에 선언되어 있고 Exception 클래스에서 오버라이딩한 메서드 중 자주 쓰이는 친구들
    - getMessage() : 예외 메시지를 String 형태로 제공받는다.
    - toString() : 예외 메시지를 Stinrg 형태로 제공받으나, getMessage() 보다 자세하게 예외 클래스 이름도 제공된다.
    - printStackTrace() : 첫 줄에는 예외 메시지, 두 번째 줄부터는 예외 원인이 되는 메서드들의 호출 관계(스택 트레이스)를 출력해준다.

## throw와 throws

- 메서드를 선언할 때 매개 변수 소괄호 뒤에 throws란 예약어를 적어준 뒤 예외를 선언하면 해당 메서드에서 선언한 예외가 발생했을 때 호출한 메서드로 예외가 전달된다.
    - 만약 2가지 이상의 예외를 던질 수 있다면 콤마로 구분하여 예외 클래스 이름을 적어준다.

![1](https://user-images.githubusercontent.com/56379649/209821848-b21ea68f-d3c3-4319-854b-0f1fdc525d81.png)

![2](https://user-images.githubusercontent.com/56379649/209821858-0ea9c235-0f22-4967-8f1b-501929519ac5.png)

- try문 내 예외를 발생시킬 경우 throw라는 예약어를 적어준 뒤 예외 객체를 생성하거나, 생성되어있는 객체를 명시해준다.
    - throw한 예외 클래스가 catch 블록 내 선언되어있지 않거나, throw 선언에 포함되어 있지 않으면 컴파일 에러가 발생한다.
- catch 블록에서 예외를 throw할 경우 메서드 선언의 throws 구문에 해당 예외가 정의되어 있어야한다.

### 정리

- 임의의 예외 클래스를 만들 경우 반드시 try-catch 문으로 묶어줄 필요가 있을 경우에만 Exception 클래스를 확장한다. 일반적으로 실행 시 예외를 처리할 수 있는 경우에만 RuntimeException 클래스를 확장하는 것을 권장한다.
- catch문 내 아무런 작업없이 공백으로 둘 경우 예외 분석이 어려우므로 로그 처리 등의 작업을 해준다.
