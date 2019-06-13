# 음식 추천 분류기 (Meal Planner)


## 진행 상황
#### 1. Dataset // 데이터셋 변경 요망
  - [선정한 이미지 데이터 셋](http://www.aihub.or.kr/content/140)
    - 150개의 카테고리 x 이미지 1,000장 = 150,000장

      - 구이	갈비구이, 갈치구이, 고등어구이, 곱창구이, 닭갈비, 더덕구이, 떡갈비, 불고기, 삼겹살, 장어구이, 조개구이, 황태구이, 훈제오리	
      - 국	계란국, 떡국/만두국, 무국, 미역국, 북엇국, 소고기무국, 시래기국, 육개장, 콩나물국
      - 김치	갓김치, 깍두기, 나박김치, 무생채, 배추김치, 백김치, 부추김치, 열무김치, 오이소박이, 총각김치, 파김치	
      - 나물	가지볶음, 고사리나물, 미역줄기볶음, 숙주나물, 시금치나물, 애호박볶음
      - 떡	경단	만두	만두
      - 면	막국수, 물냉면, 비빔냉면, 수제비, 열무국수, 잔치국수, 쫄면, 칼국수, 콩국수, 라면, 자장면, 짬뽕	
      - 무침	고추된장무침, 꽈리고추무침, 도토묵, 잡채, 도라지무침, 콩나물무침, 홍어무침
      - 밥	김밥, 김치볶음밥, 비빔밥, 새우볶음밥, 알밥, 잡곡밥, 주먹밥, 유부초밥	
      - 볶음	건새우볶음, 오징어채볶음, 감자채볶음, 고추장진미채볶음, 두부김치, 떡볶이, 라뽂이, 멸치볶음, 소세지볶음, 어묵볶음, 제육볶음, 주꾸미볶음
      - 쌈	보쌈	
      - 음청류	수정과, 식혜

  - 모델 선정을 위한 테스트에 사용한 테스트용 스몰 데이터셋  
    - 30개 카테고리 x 이미지 300장 = 9,000장

    카테고리 : 갈비탕, 갈비구이, 감자채볶음, 계란찜, 김밥, 만두, 물회, 배추김치, 꼬막찜, 된장찌개, 떡볶이, 만두, 물회, 배추김치, 삼계탕, 새우튀김,     소세지볶음, 순대, 식혜, 약과, 자장면, 족발, 찜닭, 콩자반, 피자, 한과, 해물찜, 후라이드치킨
***
#### 2. Imgage Preprocessing
  - imagedatageneration
#### 3. Conv Neural Network
  - 계획
    - 모델 조사
    - [모델 선정(1차 선정)](https://github.com/sorachin/AI_Team10/issues/16)
    - [모델 테스트(2차 선정)](https://github.com/sorachin/AI_Team10/issues/16)

#### 4. 모델 성능 개선
  - 데이터 셋
  - 데이터 전처리
    - [Augmentation (사용 계획 중)](https://github.com/sorachin/AI_Team10/issues/9)
  - 모델
    - [Pre-training](https://github.com/sorachin/AI_Team10/issues/10)
      - feature extraction (현)
      - [fine tuning](https://github.com/sorachin/AI_Team10/issues/25)
      - [tensorflow hub image classfication 예제](https://www.tensorflow.org/tutorials/images/hub_with_keras)
    - Fully-connected 계층 개선 [논문에 작성된 계층을 참고할 예정](https://www.eiric.or.kr/community/post2_cseric.php?m=view&gubun=201804&num=15137&pg=5&seGubun=10&seGubun1=&SnxGubun=%C6%F7%BD%BA%C5%CD&searchBy=&searchWord=)
    
#### 5. 모델 테스트
  - [모델 테스트](https://github.com/sorachin/AI_Team10/issues/20) : small_data + trained model(feature extraction) + fc
  - [모델 테스트2](https://github.com/sorachin/AI_Team10/issues/21) : datad(16class x 1,000장) + trained model(feature extraction) + fc
## 향후 계획
### 모델 성능 개선
- 이미지 추가
- [fine tuning](https://github.com/sorachin/AI_Team10/issues/10)
- [Batch nomarlization](https://github.com/sorachin/AI_Team10/issues/11)
- [Augmentation](https://github.com/sorachin/AI_Team10/issues/9)
- [CallBack을 통한 학습 제어](https://github.com/sorachin/AI_Team10/issues/14)
- [hyperparmeter optimization](https://github.com/sorachin/AI_Team10/issues/12)
- 모델 평가를 시각화하여 분석(텐서보드)

### 모델 성능 평가
- 텐서보드

### 음식 추천 구현 // 추가 요망
- 사용자 정보
   - 칼로리
   - 선호 음식
   - 기분
- 방법
   - 이전에 촬영한 음식을 인식, 칼로리를 측정하여 추천 칼로리를 가진 음식들을 선정
   - 나이대 별, 성별, 기분 별 기준을 정해 추천 음식들 선정
   - 이전에 먹은 음식 종류 제외
   - 위 기준에서 가중치가 높은 음식을 추천, 동률이 있다면 그 중 랜덤으로 출력

## 회의록
  #### 1 차 회의: 주제 선정
    - 영문법 자동 체크
    - 뉴스 분류기
    - 음식 추천 분류기
    - 버섯 분류기
    ∙ 위 네 가지 주제 중 음식 추천 분류기로 선정
    ∙ 이 후 각자 음식 추천 분류기에 대해 학습
  #### 2 차 회의: 음식 추천 분류기 설계
    - 사용자가 식사 중인 사진을 찍는다
    - 사진을 인식하여 음식 종류를 분류한다
    - 사용자의 정보를 입력한다 (나이, 키, 몸무게, 성별, 기분 등)
    - 식사한 음식과 사용자 정보를 토대로 음식을 추천해 준다  
  #### 3 차 회의: 역할 분담 및 계획서 작성, CNN 학습
   [계획서](https://github.com/sorachin/AI_Team10/files/3175674/default.pdf)
   
   [CNN 동영상 강의](https://www.youtube.com/watch?v=E9Xh_fc9KnQ&list=PLlMkM4tgfjnLSOjrEJN31gZATbcj_MpUm&index=38)
  #### 4 차 회의: 자료 조사 및 자료 수집
    - 김태주: 한식 이미지 데이터 (한국정보화진흥원)
    - 진소라: 대표적인 기분 표현
    - 황태희: 음식별 칼로리 
  #### 5 차 회의: Tensorflow와 Keras 학습 
   [Tensorflow](https://www.udacity.com/course/intro-to-tensorflow-for-deep-learning--ud187)
   
   [Keras](https://github.com/sorachin/AI_Team10/issues/9)
   
   [데이터 관련 학습](https://github.com/sorachin/AI_Team10/issues/3)
  #### 6 차 회의: 데이터 전처리 및 간단한 학습
    - 간단하게 3 개의 클래스로 모델 학습
  #### 7 차 회의: 데이터를 이용한 CNN 모델 테스트
   [모델 테스트](https://github.com/sorachin/AI_Team10/issues/20) : small_data + trained model(feature extraction) + fc
  #### 8 차 회의: 향후 계획 설계 및 중간점검 보고서 작성
  
  #### 9 차 회의


###
## 참고 URL
- [Matplot 한글폰트](https://programmers.co.kr/learn/courses/21/lessons/950)

- [한식 이미지 분류에서의 미리 학습 된 컨볼루셔널 뉴럴 네트워크 간 성능 비교 분석](https://www.eiric.or.kr/community/post2_cseric.php?m=view&gubun=201804&num=15137&pg=5&seGubun=10&seGubun1=&SnxGubun=%C6%F7%BD%BA%C5%CD&searchBy=&searchWord=)

- [tensorflow hub 예제](https://www.tensorflow.org/tutorials/images/hub_with_keras)

- [학습1](https://github.com/sorachin/AI_Team10/issues/5)

- [학습2](https://github.com/sorachin/AI_Team10/issues/3)

- [Keras 블로그](https://tykimos.github.io/)

- [Keras](https://keras.io/)

## 참고 서적
- [케라스 창시자에게 배우는 딥러닝(저자: 프랑소와 숄레)](https://book.naver.com/bookdb/book_detail.nhn?bid=14069088)

#### 팀원
  이 름 | 학 과 | 학 번
  -----|--------|------
  **김태주**|**무인이동체공학**|**17013247**
  진소라|디지털컨텐츠|14011195
  황태희|무인이동체공학|17013254
