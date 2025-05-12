# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 양지웅
- 리뷰어 : 이주연


# PRT(Peer Review Template)
- [X]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - 문제에서 요구하는 최종 결과물이 첨부되었는지 확인
        - 중요! 해당 조건을 만족하는 부분을 캡쳐해 근거로 첨부
          ```python
                       plain      ResNet    
            34 layers  58.51     53.05
            50 layers  50.99     76.46
          ```
    
- [X]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 해당 코드 블럭을 왜 핵심적이라고 생각하는지 확인
    - 해당 코드 블럭에 doc string/annotation이 달려 있는지 확인
    - 해당 코드의 기능, 존재 이유, 작동 원리 등을 기술했는지 확인
    - 주석을 보고 코드 이해가 잘 되었는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          ```python
              if not is_plain:
                # 하나의 블록이 만들어지면, residual과 x를 연결
                # Downsampling이 필요한 경우 (stage3, stage4, stage5의 첫 번째 블록)
                if not is_first_stage and index_block == 0:
                    x = keras.layers.Conv2D(
                        filters=n_channels[-1], # residual 경로의 출력 채널 수와 동일하게
                        kernel_size=1,
                        strides=(2,2), # Downsampling
                        padding='same',
                        use_bias=False
                    )(x) # 현재 블록의 원본 입력 'x'에 적용
                    x = keras.layers.BatchNormalization()(x)
                # Downsampling은 없지만 채널 수가 변경되어야 하는 경우
                # (예: ResNet-50의 stage2 첫 번째 블록, 입력 채널 x.shape[-1]과 residual 출력 채널 n_channels[-1]이 다를 때)
                elif index_block == 0 and x.shape[-1] != n_channels[-1]:
                    x = keras.layers.Conv2D(
                        filters=n_channels[-1], # residual 경로의 출력 채널 수와 동일하게
                        kernel_size=1,
                        strides=(1,1), # Stride 1 (크기 유지, 채널만 변경)
                        padding='same',
                        use_bias=False
                    )(x) # 현재 블록의 원본 입력 'x'에 적용
                    x = keras.layers.BatchNormalization()(x)
                output = AddResidual()([residual, x])
                output = keras.layers.ReLU()(output)
                x = output
    
            else: # plain
                output = keras.layers.ReLU()(residual)
                x = output    
          ```
        
- [X]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 문제 원인 및 해결 과정을 잘 기록하였는지 확인
    - 프로젝트 평가 기준에 더해 추가적으로 수행한 나만의 시도, 
    실험이 기록되어 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          ```python
              plain net 기준으로 34개의 레이어를 쓴 모델이 50개의 레이어를 쓴 모델보다 점수가 높다. 네트워크가 너무 깊어지면 학습이 제대로 되지 않는 것을 알 수 있다.
              50개의 레이어를 쓴 모    델을 기준으로 ResNet이 plane net보다 검증 점수가 높은 걸 알 수 있다. 네트워크를 깊게 하여 잔차 연결을 이용하면 학습에 훨씬 도움이 되는 것을 알 수 있다.
          ```
        
- [X]  **4. 회고를 잘 작성했나요?**
    - 주어진 문제를 해결하는 완성된 코드 내지 프로젝트 결과물에 대해
    배운점과 아쉬운점, 느낀점 등이 기록되어 있는지 확인
    - 전체 코드 실행 플로우를 그래프로 그려서 이해를 돕고 있는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          ```python
          회고
            50개 레이어 모델에서 월등한 검증 점수가 나오는 것을 보고 깊은 네트워크가 학습에 도움이 된다는 것과 잔차 연결이 학습에 도움이 된다는 것을 잘 알았다.
            시간이 부족해서 epoch를 크게 못했는데 epoch를 크게하여 실험해보는 것도 의미가 있을 거 같다.
          ```
        
- [X]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부
          ```python
            def build_resnet(input_shape, is_50, is_plain = False):
                # [n_blocks, n_convs, kernel_sizes, n_channels]
                config34 = {
                    'stage2': [3, 2, [3, 3], [64, 64]],
                    'stage3': [4, 2, [3, 3], [128, 128]],
                    'stage4': [6, 2, [3, 3], [256, 256]],
                    'stage5': [3, 2, [3, 3], [512, 512]]
                }
            
                config50 = {
                    'stage2': [3, 3, [1, 3, 1], [64, 64, 256]],
                    'stage3': [4, 3, [1, 3, 1], [128, 128, 512]],
                    'stage4': [6, 3, [1, 3, 1], [256, 256, 1024]],
                    'stage5': [3, 3, [1, 3, 1], [512, 512, 2048]]
                }
            
                input_layer = keras.layers.Input(shape=input_shape)
                output = input_layer    
          ```


# 회고(참고 링크 및 코드 개선)
```
# 리뷰어의 회고를 작성합니다.
# 코드 리뷰 시 참고한 링크가 있다면 링크와 간략한 설명을 첨부합니다.
# 코드 리뷰를 통해 개선한 코드가 있다면 코드와 간략한 설명을 첨부합니다.

#마무리 해석까지 잘 작성되어 있었습니다.
#딕셔너리를 사용해서 가독성 있게 코드 작성을 해주셨습니다
```
