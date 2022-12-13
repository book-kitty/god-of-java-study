> 정리
> 


- 자료 구조 : 데이터를 저장하기 위한 구조

- 배열 선언
    - int [] lottoNumbers = new int[7];
    - int [] lottoNumbers;  lottoNumbers = new int[7];

- 모든 참조 자료형은 초기화(new)를 하지 않으면 null값을 띈다.

- 배열을 선언과 함께 초기화할 때 두 줄에 걸쳐 선언되어 있으면 컴파일 에러가 발생하여 반드시 한번에 변수 선언 및 초기화가 이뤄져야 한다.
    - int []lottoNumbers; lottoNumbers = {1,2,3}; [X] => "Array initializer is not allowed here"
    - int []lottoNumbers = {1,2,3}; [O]

- 2차원 배열의 선언
    - int twoArr[][] = new int[2][];    // [O]
    - int twoArr[][] = new int[][];     // Array initializer expected
    - int twoArr[][] = new int[][2];    // 1차원 배열 미지정
