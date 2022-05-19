# keras

[참고자료](https://wikidocs.net/32105)

## 활성화 함수

> 딥러닝 네트워크에서 노드에 입력된 값들을 비선형 함수에 통과시킨 후 다음 레이어로 전달하는데, 이 때 사용하는 함수를 >
> 활성화 함수(Activation Function)라고 한다.
> 
> 선형 함수가 아니라 비선형 함수를 사용하는 이유는 딥러닝 모델의 레이어 층을 깊게 가져갈 수 있기 때문이다.

> 인공신경망에서 활성화 함수는 입력 데이터를 다음 레이어로 어떻게 출력하느냐를 결정하는 역할이기 때문에 매우 중요하다.
> 즉, 활성화 함수는 입력을 받아서 활성화 또는 비활성화를 결정하는 데에 사용되는 함수이다.

- linear : 디폴트 값으로 별도 활성화 함수 없이 입력 뉴런과 가중치의 계산 결과 그대로 출력.
- sigmoid : 이진 분류 문제에서 출력층에 주로 사용되는 활성화 함수.
- softmax : 셋 이상의 선택지 중 하나를 택하는 다중 클래스 분류 문제에서 출력층에 주로 사용되는 활성화 함수.
- relu : 은닉층에 주로 사용되는 활성화 함수.

## Sequential
---


## Dense
---
모델 구성

첫번째 인자 = 출력 뉴런의 수.

input_dim = 입력 뉴런의 수. (입력의 차원)

activation = 활성화 함수.
``` 
# ex
model.add(Dense(12, input_dim=8, activation='relu'))
model.add(Dense(8, activation='relu'))
model.add(Dense(1, activation='sigmoid')) 
```

## compile
---
