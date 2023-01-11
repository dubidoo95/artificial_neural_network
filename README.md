# artificial_neural_network

## 1. Introduction
![image](https://user-images.githubusercontent.com/110075956/211739950-55e49662-cff3-4f36-b42e-9e98d50d80d7.png)
artificial neural network(ANN, 인공신경망)란, 인간의 뉴런을 본떠 만든 기계학습 알고리즘입니다. <br><br>
크게 input layer, hidden layer, output layer로 구성되어 있습니다. <br><br>
input layer에서 입력 받은 값은 각각의 값에 가중치(weight)를 곱하고 편향(bias)를 더해 다음 층인 hidden layer로 갑니다. hidden layer에서 다시 가중치를 곱하고 편향을 더해 다음 hidden layer로 갑니다. 일련의 과정을 거친 후 마지막 output layer에 도달하면 값을 출력하는 것이 ANN의 기본 구조입니다. <br><br>
이 때 단순히 가중치를 곱하고 편향을 더하는 과정만 반복한다면 선형성을 잃지 않기 때문에 output layer는 input layer에 행렬을 하나 곱한 것과 같아집니다. 따라서 각 layer마다 활성화 함수(activation function)라는 것을 적용시켜 모델의 비선형성을 만들어냅니다.

## 2. Data
데이터는 다음과 같습니다.

![image](https://user-images.githubusercontent.com/110075956/211739345-071a51d9-aa47-4227-ae8f-25dc2990452b.png)

임의의 숫자 $20\times8$개의 데이터와 0과 1로 구성된 $20\times1$개의 데이터로 구성되어 있습니다. <br>
x1~x8열의 데이터를 통해 y열의 값을 예측하는, 이진분류에 해당하는 데이터입니다.

## 3. Pipeline
파이프라인은 다음과 같습니다.
![image](https://user-images.githubusercontent.com/110075956/211741796-8929fe3b-f76f-4710-8a99-b2960b7692a1.png)
1. data_load()를 통해 데이터를 호출합니다. <br>
2. data_split()을 통해 데이터를 섞고, 데이터를 train dataset과 test dataset으로 나눕니다. 그리고 x1~x8열의 데이터를 특성으로, y열의 데이터를 레이블로 지정합니다. <br>
3. ANN()을 통해 인공신경망 모델을 호출합니다. <br>
4. BCELoss()를 통해 손실 함수를 호출합니다. <br>
5. train()을 통해 모델을 훈련시킵니다. <br>
6. evaluate()를 통해 훈련시킨 모델의 성능을 검증합니다.<br>

## 4. Result
![image](https://user-images.githubusercontent.com/110075956/211742464-00eea368-67e7-412a-a59d-2bde9c8700de.png)

## 5. Conclusion
1. 역전파를 통한 가중치와 편향의 업데이트를 거치지 않았기 때문에 loss가 높고 accuracy가 낮습니다.

2. hidden layer를 통과하지 않고 input layer에서 바로 output layer로 넘어갔기 때문에 성능이 좋지 않습니다.
