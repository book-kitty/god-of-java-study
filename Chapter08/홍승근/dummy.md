## static
```java
  public class ReferenceStatic{
    public static void main(String args[]){
      ReferenceStatic.staticMethod();
    }
    public static void staticMethod(){
      System.out.println("this is a staticMethod.");
    }
  }
```
> 이 예시대로 메소드의 리턴 타입 앞에 static이 붙게 되면 static 메소드가 되며 이 static메소드는 객체를 new로 생성하지 않아도 바로 호출이 가능하게 된다.

## static 블록
```java
   static {
   //코드
   }
```
* static 블록은 위와 같이 생겼으며, 객체가 생성되기 전에 딱 한번만 호출이 된다.
* static 블록은 클래스 내에만 선언할 수 있고, 메소드 내에서는 선언할 수 없다.
* 실행 순서
  1. 클래스가 로딩이 됨
  2. 클래스 변수가 있으면 메모리를 생성
  3. static 블록이 선언된 순서대로 실행

## 매개변수 개수를 특정 지을 수 없을 때
> 매개변수에 배열이 들어갈 수도 있고 아닐 수도 있는 상황이 있을 때 사용가능한 방법이다.
```java
  public class ArrayTest {
    public static void main(String[] args) {
        int[] arrayValues = {1,2,3,4,5};
        int value1 = 1;
        int value2 = 3;
        ArrayTest arrayTest = new ArrayTest();
        arrayTest.test(arrayValues);
        arrayTest.test(value1, value2);
    }

    public void test(int...values){
        for (int value:values){
            System.out.println(value);
        }
    }
}
```
> 위와 같은 코드처럼 메소드에 int...values로 매개변수를 받았을 때 int[] 변수도 들어갈수 있고 int 변수들이 여러개가 들어갈 수 있게 된다.
> 단, int[] 변수와 int 변수를 같이 매개변수로 넘겨주는 것은 사용이 불가하다.
