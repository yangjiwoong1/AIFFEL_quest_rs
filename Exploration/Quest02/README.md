# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 양지웅
- 리뷰어 : 이현재


# PRT(Peer Review Template)
- [O]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - Public score 기준 110000점 이하의 성능을 보여주었다.
        - ![image](https://github.com/user-attachments/assets/b506c748-cee3-4dcd-9f26-fc8d6cd3e715)

    
- [O]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - Feature Engineering 과정에서 각 라인마다 기존의 feature를 어떤 근거로 새로운 feature를 만들었는지 기술했다.
        - ![image](https://github.com/user-attachments/assets/8ad93dfe-49a7-4052-a3af-7f4ba6e6305c)
    - Scatter plot에서 이상치 확인 후, 제거하는 부분을 주석으로 제시해 가독성이 좋았다.
        - ![image](https://github.com/user-attachments/assets/cbda5ba2-a650-4dd7-b551-35a7d5a1248c)
    


        
- [O]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 실험 과정에서 모델 학습 결과가 좋았던 방법을 주석으로 제시해줬다.
        - ![image](https://github.com/user-attachments/assets/bb2696b1-8bb0-4e35-8c66-cc5679faeadf)
        - ![image](https://github.com/user-attachments/assets/98a598de-4498-4dfd-a872-4e9011c69f8f)
        - ![image](https://github.com/user-attachments/assets/90c02700-b848-4015-b7eb-2c148f0bd2fb)



        
- [O]  **4. 회고를 잘 작성했나요?**
   

        
- [O]  **5. 코드가 간결하고 효율적인가요?**
    - 파이썬 스타일 가이드 (PEP8) 를 준수하였는지 확인
    - 코드 중복을 최소화하고 범용적으로 사용할 수 있도록 함수화/모듈화했는지 확인
        - 중요! 잘 작성되었다고 생각되는 부분을 캡쳐해 근거로 첨부


# 회고(참고 링크 및 코드 개선)
```
Feature Engineering을 철저히 한 부분이 인상적이었다. 나도 각 Feature의 의미를 좀 더 면밀히 살펴보고 Feature Engineering을 할 때 더 신경을 써야겠다는 생각이 들었다.
모델을 LightGBM만 쓰고도 좋은 성능을 내서 인상적이었다. Feature Engineering과 하이퍼 파라미터 튜닝에 더 신경쓰면 Ensembling을 굳이 할 필요가 없을 수 있겠다.
```
