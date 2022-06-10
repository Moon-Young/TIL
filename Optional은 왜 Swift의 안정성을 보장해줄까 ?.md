# Optional은 왜 Swift의 안정성을 보장해줄까요 ?

### Swift의 언어 안정성에 기본 바탕에는 Optional 이라는 개념이 중요하게 자리 잡고있어요.

</br>

<code>
  let myFirstOptionalVar: Int?
</code>

#### Optional은 nil을 사용할 수 있는 타입과 없는 타입을 구분하기 위함이고, nil을 사용할 수 있는 Type를 Optional Type이라고 해요.
#### → 정의하면 'nil' 값을 가질 수 있으면 Optional Type이고, 선언할 땐 Type 옆에 '?'를 붙이면 됩니다.
</br>

### 그렇다면 'nil'은 무엇일까요 ?
#### 'nil'은 보통 다른 언어에서는 'null'이라고 하는 "값이 없음"을 의미해요.
#### 값이 없음의 의미는 방금 오류가 발생하였지만 앱 크래시를 발생시키지는 않을게 대신 'nil'을 리턴해줄테니 오류를 고쳐라는 의미가 있어요.
#### 그래서 Optional은 Swift의 안정성을 보장해준다고 할 수 있어요.

![스크린샷 2022-06-10 오후 4 33 45](https://user-images.githubusercontent.com/29904301/173014365-4679c76c-40a0-4366-8759-0b956e6353c2.png)


#### 존재 하지 않는 키 값에 접근을 했기에 오류이지만 컴파일 에러를 최소화 하고자 그냥 오류라고만 알려주려고해요.
#### 그렇다고 리턴값을 공백이나 0으로는 리턴해줄 수 없기에 앞에서 말한'nil'을 사용하는거에요.(이해 안되면 다시 읽기)

</br>

### Non-Optional Type vs Optional Type
#### 'nil은 특수한 값이기 때문에 일반적으로 쓰이는 자료형에는 담지 못하는데 그게 바로 'nil을 담지 못하는 타입이 'Non-Optional Type'
#### Non-Optional Type의 특징은 무조건 '값을 가지고 있어야 되는거에요.
#### 아래처럼 Non-Optional Type면서 값을 넣지 않고 접근하면 에러가 나요.

![스크린샷 2022-06-10 오후 4 23 59](https://user-images.githubusercontent.com/29904301/173012690-7f03a41a-2846-4300-8854-d8852c6ee89f.png)

#### 그렇다면 Non-Optional Type에 'nil을 넣으면 접근 할 수 있을까요 ?

![스크린샷 2022-06-10 오후 4 25 31](https://user-images.githubusercontent.com/29904301/173012955-722bd02d-39e1-49c0-8c08-0b5131778639.png)

#### 정답은 'NO!' nil은 Optional-Type에만 넣을 수 있음.
#### nil을 넣는 방법은 2가지

#### Type Annotation - 자료형(Type)의 뒤에 '?' 붙여주기
![image](https://user-images.githubusercontent.com/29904301/173018007-dcf952e1-4151-4e6d-a28f-d848a55a036d.png)

#### Type Inference - 추론을 옵셔널 타입으로 추론하게끔 값을 넣는 방법
![image](https://user-images.githubusercontent.com/29904301/173019872-21d949df-f6b0-4176-966f-a94229b548c7.png)

#### 위에 human dictionary는 왜 nil로 나왔을까요 ?
![image](https://user-images.githubusercontent.com/29904301/173020070-419993df-73b9-40fe-9d15-6b6c2571cd48.png)

#### dictionary에서 value 리턴값이 Value?로 선언되어 있기 때문이에요.

![스크린샷 2022-06-10 오후 5 09 33](https://user-images.githubusercontent.com/29904301/173021204-c2e4110c-baf9-4425-8bce-f83c128be86e.png)

#### 결국 Optional Type는 한번 더 감싼 Type라고 생각하면 쉬워요.
<img width="394" alt="스크린샷 2022-06-10 오후 5 15 44" src="https://user-images.githubusercontent.com/29904301/173022252-0942537c-a199-40a5-a58e-10a8b3d46698.png">

### 옵셔널이란 포장지로 자료형을 한번 포장했기 때문에 다시 값을 사용하려면 포장지를 까야는데 그걸 Unwrapping이라고 해요.(다음 TIL에서..)

