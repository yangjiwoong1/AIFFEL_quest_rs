# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 양지웅
- 리뷰어 : 김성훈


# PRT(Peer Review Template)
- [x]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - Simple Baseline 구현
    - ![image](https://github.com/user-attachments/assets/8e9500a5-185e-4c97-97f8-9c5fa227cf15)

    - Simple Baseline 모델의 예측 결과
    - ![image](https://github.com/user-attachments/assets/cced1a7a-0cfb-4dcd-9286-544ec4928cb7)
    
    - Stacked Hourglass 모델 예측 결과
    - ![image](https://github.com/user-attachments/assets/f71bcd98-9e6d-4587-a1a9-24a24b03c177)

    
- [x]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 각 코드 블럭 시작에 앞서 어떤 부분을 적용했는지 언급
    - ![image](https://github.com/user-attachments/assets/b34df966-06cc-40f6-9dc1-f6f1edc30766)
    - ![image](https://github.com/user-attachments/assets/0a1fd81d-373c-4564-9a3c-a51629b9cc5c)

    - Simple Baseline 모델의 Resnet 구조 Trainable 등을 변경해가며 여러 모델로 실험 진행
        
- [x]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 모델의 예측 결과 성능을 개선하기 위해 모델의 학습 가능 파라미터를 조절해가며 변화를 확인

        
- [x]  **4. 회고를 잘 작성했나요?**
    - 프로젝트 진행 시 발생한 이슈와 이를 해결하기 위한 시도 및 그 결과 등에 대해 기록
    - 아쉬운점과 교훈 등을 기록 
        
- [x]  **5. 코드가 간결하고 효율적인가요?**
    - 각 작업을 수행하는 코드를 함수로 모듈화 사용하여 사용.


# 회고(참고 링크 및 코드 개선)
```
- 발생한 문제 및 성능 개선을 위한 시도로 Trainable 파라미터를 변수로 적용한 부분이 인상 깊었습니다.
- Simple Baseline의 경우 compute_loss 함수에서 For문으로 인한 Loss 계산 오류가 발생한 것은 아닌지 의심됩니다.
- Simple Baseline 학습에서 발생한 이슈가 해결된다면 Resnet의 튜닝 유무로 발생하는 결과 차이까지 볼 수 있는 부분이 기대됩니다.
```
