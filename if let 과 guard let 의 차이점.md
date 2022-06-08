# if let 과 guard let 의 차이점은 무엇일까요 !

문득 guard let을 주로 쓰는 이유가 궁굼해서 공부해봄.<br>
3~4가지 이유가 있지만 내가 가장 느낀 이유는 역시 바인딩 된 변수의 scope의 차이.

## if let
- 단순히 옵셔널 처리 값에 대한 피드백만 주고 싶을 때
- 너 값 있으면 이렇게 처리하고 nil 이면 저렇게 처리해!
<img width="366" alt="image" src="https://user-images.githubusercontent.com/29904301/172042890-3e4467d8-ce00-4d8e-b6d9-0294fe0667c0.png">


## guard let
- 옵셔널 처리 값이 nil인 경우 무조건 함수의 실행을 종료 시킬 때
- 너 값 없니? 그럼 내 함수에서 나가

<img width="389" alt="image" src="https://user-images.githubusercontent.com/29904301/172043079-3989e16d-ada0-4197-b311-2ae8a8622da4.png">



## ⚠︎ guard let 과 if let 차이점.


1. if let 안에서의 언랩핑된 변수의 scope는 local variable 로 scope 벗어나면 사용이 불가능해요. <br>
<img width="683" alt="image" src="https://user-images.githubusercontent.com/29904301/172043115-11760ebc-35ef-446e-8054-cbc9e6b55da4.png">

2. 반대로 guard let은 바인딩된 변수의 scope는 global variable 로 local variable에서는 사용이 불가능해요. 
<img width="718" alt="image" src="https://user-images.githubusercontent.com/29904301/172043327-c3c99dc4-447a-48ad-8c7f-9ac7c251d048.png">


<br>
<br>
> https://babbab2.tistory.com/17
