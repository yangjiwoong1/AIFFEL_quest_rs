# AIFFEL Campus Online Code Peer Review Templete
- 코더 : 양지웅
- 리뷰어 : 강희봉


# PRT(Peer Review Template)
- [O]  **1. 주어진 문제를 해결하는 완성된 코드가 제출되었나요?**
    - diabetes : 3000 이하의 MSE 만족 & 첫번째 컬럼에 대한예측 시각화 첨부
      ![image](https://github.com/user-attachments/assets/d9b51450-29a7-4297-8b46-abec1dc62ba4)
    - bike_sharing_demand : 150 이하의 RMSE 만족 & 데이터 개수 시각화 및 최종 결과 시각화 모두 첨부
      ![image](https://github.com/user-attachments/assets/b9262f3e-116e-43cb-9d3e-3c979ddb669e)
      ![image](https://github.com/user-attachments/assets/7e638822-7aa3-4b71-84e2-c87e52ac5a43)
      ![image](https://github.com/user-attachments/assets/8b1b82c8-18cf-4fbc-8471-f1882a4b0e7d)

- [O]  **2. 전체 코드에서 가장 핵심적이거나 가장 복잡하고 이해하기 어려운 부분에 작성된 
주석 또는 doc string을 보고 해당 코드가 잘 이해되었나요?**
    - 배운 내용과 거의 동일한 코드를 작성하는 Quest라 다르게 접근한 부분 위주로 평가하였습니다. 
    - predict 함수를 배운 내용과 다른 방식으로 작성했는데 이해하기 쉽게 주석을 달아두었습니다.
      ![image](https://github.com/user-attachments/assets/e34eb384-47c4-47d7-878a-a5a6695cf669)
    - 특별히 서로 다른 부분이 없을 프로젝트라 다르게 접근한 부분을  season 값을 one hot 인코딩으로 처리한 부분이 인상적이었습니다. 해당 부분의 변경으로 대부분 비슷하게 나왔을 RMSE 값이 141.xxx인데 140.xxx로 나온 것을 확인할 수 있었습니다.
      ![image](https://github.com/user-attachments/assets/5f77e786-dee6-4490-ab4a-9deb411ebb50)
 
        
- [O]  **3. 에러가 난 부분을 디버깅하여 문제를 해결한 기록을 남겼거나
새로운 시도 또는 추가 실험을 수행해봤나요?**
    - 바로 위에 나온 season 을 원핫 인코딩으로 변경한 부분도 새로운 시도로 볼 수 있습니다(중복이라 캡쳐 생략)
    - 학습률과 epoch 를 변경하며 실험한 내용이 기록되어있습니다.
      ![image](https://github.com/user-attachments/assets/7b995766-8b8f-48c0-bbca-78aac137a70c)
        
- [X]  **4. 회고를 잘 작성했나요?**
    - 회고작성 안함. 회고를 코드내에 작성하는 것인지 몰라서 코드 설명시에 서로 회고 내용을 이야기했습니다.  
        
- [O]  **5. 코드가 간결하고 효율적인가요?**
    - 전체적으로 효율적으로 작성된것으로 보입니다. 특히 예측 모델을 클래스화한 부분이 인상적이었습니다.
      ![image](https://github.com/user-attachments/assets/250ed595-2e89-46a1-ba1e-9ddf690725d5)



# 회고(참고 링크 및 코드 개선)

제공된 프로젝트 수행플로우가 아닌 모듈, 함수 정의, 클래스 정의, 훈련, 테스트, 시각화등으로 나누어 코드를 작성한 부분이 인상적이었으며 익숙한 언어로 작성시에는 깔끔한 코드에 대해 신경쓰던 것을 배우는 과정이라고 무시하고 문제 해결에만 급급하게 코드를 작성하고 있었구나 생각했습니다. 노트북파일에서 코드블럭외 마크다운 블럭을 추가해 깔끔하게 정리할 수 있다는 것도 배울 수 있는 코드 리뷰였습니다. 리뷰어가 얻어가는 것이 더 많은 리뷰였다고 생각합니다. 코드보다는 학습 사용할 컬럼 선택에 관한 부분에 대해서 이야기들을 해드렸는데 도움이 되었길 바랍니다. 
