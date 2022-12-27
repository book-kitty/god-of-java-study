# chapter14. 다 배운 것 같지만, 예외라는 중요한 것이 있어요.

### 자바에서 매우 중요한 예외
> 자바에서 예외(Exception)이란 "우리가 예상한, 혹은 예상치도 못한 일이 발생하는 것을 밀 ㅣ예견하고 안전장치를 하는 것"을 말한다.   

### try-catch는 짝이다
>- try-catch 에서 예외가 발생하지 않을 경우   
>try 내에 있는 모든 문장이 실행되고 try-catch 문장 이후의 내용이 실행된다.
>- try-catch 에서 예외가 발생하는 경우   
  try 내에서 예외가 발생한 이후의 문장들은 실행되지 않는다.   
  catch 내에 있는 문장은 반드시 실행되고, try-catch 문장 이후의 내용이 실행된다.

### try-catch를 사용하면서 처음에 적응하기 힘든 변수 선언
> try-catch를 사용할 때 가장 하기 쉬운 실수가 있다.   
> try 블록은 말 그대로 중괄호로 쌓여 있는 블록이다. 따라서 try 내에서 선언한 변수는 catch 내에서 사용할 수 없다.   
> 때문에 catch에서 사용하는 변수는 대부분 try 블록 전에 선언해야 한다.

### finally야~ 넌 무슨 일이 생겨도 반드시 실행해야 돼
> try-catch 구문에 추가로 붙을 수 있는 블록이 바로 **finally**다.   
> 자바에서 예외를 처리할 때 finally는 "어떠한 경우에도 반드시 실행해"라는 의미이다.   
> finally 블록은 코드의 중복을 피하기 위해서 반드시 필요하다.
 
### 두 개 이상의 catch
> - try 다음에 오는 catch 블록은 1개 이상 올 수 있다.   
> - 먼저 선언한 catch 블록의 예외 클래스가 다음에 선언한 catch 블록의 부모에 속하면, 자식에   
> 속하는 catch 블록은 절대 실행될 리가 없으므로 컴파일이 되지 않는다.
> - 하나의 try 블록에서 예외가 발생하면 그 예외와 관련이 있는 catch 블록을 찾아서 실행한다.

### 예외의 종류는 세 가지다
> 예외의 종류는 세 가지다.
> - checked exception
> - error
> - runtime exception 혹은 unchecked exception

#### error
> 에러는 자바 프로그램 밖에서 발생한 예외를 말한다.
> Error 와 Exception으로 끝나는 오류의 가장 큰 차이는 프로그램 안에서 발생했는지, 밖에서 발생했는지 여부이다.   
> 더 정확하게 말하면 Error는 프로세스에 영향을 주고, Exception은 쓰레드에만 영향을 준다.

#### runtime exception (이하 런타임 예외)
> 런타임 예외는 예외가 발생할 것을 미리 감지하지 못했을 때 발생한다.   
> 이 런타임 예외에 해당하는 모든 예외들은 RuntimeException을 확장한 예외들이다. 컴파일시에 체크를 하지 않기 때문에 unchecked exception 이라고도 부른다.   

#### 모든 예외의 할아버지는 java.lang.Throwable 클래스다.
> Exception과 Error 클래스는 Throwable 클래스를 상속받아 처리하도록 되어 있다.   
> 이는 모두 동일한 메소드를 사용하여 처리할 수 있도록 하기 위함이다.   
> 많이 사용하는 메소드에는 getMessage(), toString(), printStackTrace()가 있다.