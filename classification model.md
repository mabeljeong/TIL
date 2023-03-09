* Regression과 Classification model은 서로 다른 종류의 문제 해결을 위한 모델링 방법 

    * regression(회귀 모델)    
    입력 변수와 출력 변수 간의 연속적인 관계를 학습하여, 새로운 입력 값에 대한 출력 값을 예측 ex) 부동산 가격 예측, 수익 예측 
       * Linear Regression 

    * classification(분류 모델)   
    입력 데이터를 사전에 정의된 클래스 또는 범주로 분류하는데 사용, 입력 변수와 출력 변수 간의 관계를 학습하여, 새로운 입력 값에 대한 출력 값을 예측 ex) 스팸 필터링, 의료 진단, 이미지 분류

        * **Logistic Regression (for binary classification)**   
        입력 데이터와 출력 데이터(클래스) 간의 관계를 모델링하는 선형 모델
이진 분류 문제를 쉽게 해결 가능(ex. 출력값이 0,1 중에 하나인거 타이타닉에서 survived면 1이고 아니면 0인 것처럼)   
        * Support Vector Machine (회귀 모델링?)   
데이터들을 고차원 공간으로 매핑하고, 그 공간에서 최적의 경계를 찾아서 분류를 수행  
    이 결정 경계는 각 클래스에서 가장 가까운 데이터와의 거리가 최대가 되도록 함(마진 최대화)

        * **Decision Tree**    
트리기반의 분류 규칙을 만든 것
너무 과도하게 분할하면 트리가 복잡해지고 Overfitting 됨   
개선방법 - 트리가 더 이상 커지지 않게 하는 stopping rule, pruning이 있음   
결정트리는 가치지기를 사용함에도 과적합이 되는 경향이 있어 일반화 성능이 좋지않다. 이런 문제에대한 대안으로 앙상블 방법이 있다.   
**overfitting: an undesirable machine learning behavior that occurs when the machine learning model gives accurate predictions for training data but not for new data
        * **Random Forest  (decision tree 기반)**   
배깅 방법을 적용한 결정 트리의 앙상블모델   
**앙상블(ensemble): 여러 개의 분류기(classifier)를 생성하고 그 예측을 결합함으로써 보다 정확한 최종 예측을 도출하는 기법   
**bagging: 같은 학습기, 다른 데이터로 학습 후 결합
        * Ada Boost    
데이터의 가중치를 조정하여 다음 모델이 더 많은 주의를 기울일 데이터를 선택함
이진 분류 문제에서 많이 사용   
**boost: 배깅과 마찬가지로 서브 훈련 데이터 샘플을 만듦 -> 처음 샘플링은 모든 데이터에 동일 가중치를 두어 샘플링함 ->  샘플링 된 서브 훈련 데이터로 학습함 -> 분류가 잘못된 데이터의 가중치를 높이고 다시 샘플링함 -> 새로운 샘플링으로 다시 학습, 반복하여 점차 분류하기 어려운 패턴들을 많이 선택 -> 분류가 어려운 패턴에 더욱 집중하여 정확도 높임    
즉, 약한 예측 모델들을 연결하여 강력한 예측 모델을 만드는 머신 러닝 알고리즘
        * Gradient Boosting   
        각각의 예측 모델은 이전 모델의 오차를 보완해서 만들어짐    
이전 모델의 잔여오차에 대한 새로운 모델을 학습시키므로 overfitting에 취약할 수 있음
        * XGBoost   
Gradient Boosting의 한 종류로, 성능을 높이기 위해 다양한 기능을 추가한 것(높은 처리 속도, 규제, 및 병렬 처리 등) 
대규모 데이터 세트에서 매우 잘 작동
        * Light GBM   
Leaf-Wise(리프 별)방식을 사용하여, 더 많은 분할 후보군을 생성하고 분할에 대한 가중치를 계산하여 더 나은 성능을 얻을 수 있음   
작은 데이터 세트에서도 빠르게 처리 가능   
xgboost 비해 규제 기능이 상대적으로 약하며, 적절한 하이퍼파라미터 튜닝 필요 
        * Kmeans Clustering(unsupervised Learning, 위에 것들은 다 supervised learning)   
데이터 포인트들을 cluster로 묶는 알고리즘
초기 중심점을 랜덤으로 설정해서 여러번 실행하여 결과 비교 가능함   
cluster 모양이 원형에 가깝게 분포해야하며, 데이터가 밀집되어 있을 때 잘 동작함
