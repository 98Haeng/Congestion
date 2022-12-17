# Congestion
2022Yeonsei DataCampus Congestion Recommendation System Project

![파일구조](/flowchart.png)
상기의 이미지는 본 프로젝트의 폴더구조를 나타내고 있다. 최상의 폴더 MTWT 하위에 5가지 폴더를 가진다.

1. EDA  (프로젝트 주제에 맞춰 데이터 탐색, 분석 진행)
2. Data_collection (데이터를 수집하고 전처리하기 위한 코드들을 포함)
3. LSTM-Modeling (혼잡도 예측을 위한 LSTM을 모델을 생성하고 학습시키는 코드)
4. Recommender System (특정 관광지에 대해 유사한 관광지 10개를 추천해주는 코드)
5. Dataset (원본 데이터와 학습에 사용하기 위해 가공한 데이터 포함)
    * raw_data (원본 데이터)
    * final_data (모델 학습을 위해 가공한 데이터)


# EDA
 * tourist_num_EDA.ipynb : 관광형태의 변화를 이동 통신 데이터를 이용해 2019 ~ 2021년 지역별 관광객 수를 변화량을 분석하는 코드 
    - plot의 글씨가 안보일 경우, 글꼴을 설정 할 것.
(e.g. plt.rc('font', family = 'Malgun Gothic'))
    - 실행방법 : 위에서 아래로 순서대로 실행
 * 
# Data_collection
 * humidity.ipynb
 * minimum_temperature.ipynb
 * maximum_temperature.ipynb
 * type_of_rain.ipynb
 * probability_of_rain.ipynb
 * date_data.ipynb

 위의 파일 5개는 순서대로 습도, 최저기온, 최고기온, 강수형태, 강수확률을 365일 기준으로 처리하기 위한 코드임.
 
 실행방법은 위에서 아래로 순서대로 실행

 * target_j.ipynb
 * target_s.ipynb

 위의 파일은 각각 제주도와 서귀포시에 대해 정답 레이블을 전처리하기 위한 코드임.

 실행 순서는 위와 동일
    - 혼잡한 poi 41개에 대해 코드를 실행해야 하며, 각각의 poi에 대해 파일명과 조건만 지정하면 동일하게 시행됨
    - 이에 대한 출력 결과는 final data의 파일을 통해 확인할 수 있음
    - 해당 파일에서는 코드의 구현 가능성을 시험하기 위해 각각의 시에 대해 관광 poi 한 개씩 지정하여 실행
 


 실행방법 : 위와 동일

 * naverblog_crawler.ipynb
 * social_buzz_concat_weather.ipynb

 소셜 버즈량을 확인하기 위해 일자별 블로그 게시글 건수를 크롤링하기 위한 데이터임

 실행방법 : 위와 동일

# LSTM-Modeling
 * LSTM_CNNLSTM.ipynb : 다음날의 관광수요를 미리 예측하기 위해 딥러닝 모델인 LSTM과 CNN-LSTM을 RMSE로 비교 하는 코드임.
   실행 순서
    1. 제출 파일 중 MTWT/Dataset/final_data/modeling_dataset 폴더를 복사할 것.
    2. GPU를 사용하기 위해 Colab 환경에서 실행할 것
    3. drive를 mount한 후, ‘project_path’에 접근 먼저 할 것.
    4. /content/drive/My Drive/Colab Notebooks에 먼저 업로드 할 것.
    5. 순서대로 남은 코드 실행 할 것.



# Recommender System
 * Recommendation_sys.ipnyb : 사용자 사전을 반영하여 문서유사도를 구하고 그 결과로 추천시스템을 구현하는 코드임.
    - 원활한 사용자 사전 추가를 위해 Colab 환경에서 실행할 것
    - Colab 환경 '/content' 하위 폴더에 Jeju_POI_withexplanation (3).xlsx 파일과 nnp.csv 파일을 옮겨주어야 함 ![파일구조](/image.png)  
    - 두 데이터는 경로상 위치는 각각 
        - /Dataset/final_data/Jeju_POI_withexplanation (3).xlsx
        - /Dataset/final_Data/nnp.csv
    - 순서대로 코드를 설치하여 konlpy, mecab 등의 라이브러리를 설치하도록 함
