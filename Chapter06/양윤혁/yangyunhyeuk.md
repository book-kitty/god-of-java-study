> 정리
> 


- java6까지는 switch문에서 long을 제외한 enum, Character, Byte, Short, Integer 타입만 비교대상변수로 사용 가능

- java7부터는 String도 비교대상변수로 사용 가능

- switch문 내 default
    - 먼저 선행된 조건에 부합되지 않을 경우 수행하는 예약어이다.
    - 허나, 선행된 case문 내 break문이 없을 경우 처리가 끝나지 않아 default 조건까지 도달하게 되어 원치않는 결과값을 초래할 수 있다.
