# ❓14장 다 배운 것 같지만, 예외라는 중요한 것이 있어요
   
## 네 가지 종류의 변수는 어떻게 구분할 수 있을까?
예외를 처리하기 위한 세가지 블록에는 try catch finally 가 있다.<br>
첫번째 문제의 답 중에서 "여기에서 예외가 발생할 것이니 조심하세요"라고 선언하는 블록은 어떤 블록인가요? try<br>
첫번째 문제의 답 중에서 "예외가 발생하던 안하던 얘는 반드시 실행되어야 됩니다."라는 블록은 어떤 블록인가요? finally<br>
예외의 종류 세가지는 각각 error, unchecked exception, checked exception이다.<br>
프로세스에 치명적인 영향을 주는 문제가 발생한 것을 error라고 한다.<br>
try나 catch 블록 내에서 예외를 발생시키는 예약어는 throws다.<br>
메소드 선언시 어떤 예외를 던질 수도 있다고 선언할 때 사용하는 키워드는 throws다.<br>
직접 예외를 만들 때 RuntimeException 클래스의 상속을 받아야 한다.<br>


