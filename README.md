# 🎬 Movie Recommendation System (Spark 기반 추천 시스템)

MovieLens 데이터셋과 영화 줄거리/장르 정보를 활용하여  
**Collaborative Filtering 기반 영화 추천 시스템**을 구현한 프로젝트입니다.  
대규모 평점 데이터 처리를 위해 **PySpark 기반 추천 파이프라인**을 구축하고,  
여러 추천 모델(아이템 기반 CF, KNN, TF-IDF, Spark 기반 추천)을 비교 실험했습니다.

---

## 🚀 Project Goal

- 영화 평점 데이터를 기반으로 개인화 추천 결과 생성
- Spark 기반 분산 처리 환경에서 추천 시스템 구현 경험
- 장르/줄거리 등 메타데이터를 활용한 추천 품질 개선 시도
- 다양한 추천 모델 실험을 통한 성능 비교 및 인사이트 도출

---

## 👥 Team Info

- **Team Project (대학교 추천 시스템/데이터 처리 프로젝트)**
- 역할: 데이터 전처리, 모델 실험, Spark 기반 추천 구현, 추천 결과 검증

---

## 🛠 Tech Stack

- **Python**
- **Apache Spark (PySpark)**
- **Pandas / NumPy**
- **Scikit-learn**
- **Jupyter Notebook**
- **Web Crawling (영화 메타데이터 수집)**

---

## 📂 Project Structure

```bash
RecommendationSystem-main/
├── dataset/                      # MovieLens dataset + crawling 결과
│   ├── movies.csv
│   ├── ratings.csv
│   ├── tags.csv
│   ├── links.csv
│   └── movies_crawling_result.csv
│
├── Preprocessing/
│   ├── crawling/                 # 영화 정보 크롤링
│   └── preprocess/               # 데이터 전처리 및 Spark 전처리 실험
│
├── model/                        # 추천 모델 구현 및 실험
│   ├── CF- Item-based_dot product_ASL + normal.ipynb
│   ├── ITEM_RATING_knn.ipynb
│   ├── Spark_Model.ipynb
│   ├── 불Finda_Spark_movie_recommendation.ipynb
│   └── ...
│
└── README.md
```

---

## 📌 Dataset

- **MovieLens Dataset**
- 사용자-영화 평점 데이터 기반 추천 모델 학습
- 영화 장르 및 링크 데이터 포함

추가적으로, 영화 줄거리/메타 정보를 확보하기 위해  
**크롤링을 통한 데이터 확장 작업**을 진행했습니다.

---

## ⚙️ Pipeline Overview

### 1) Crawling (데이터 확장)
- MovieLens 영화 ID 기반으로 영화 정보를 크롤링
- 줄거리/장르 등의 텍스트 기반 추천 요소 확보

📍 관련 파일:
- `Preprocessing/crawling/*.ipynb`

---

### 2) Data Preprocessing
- ratings, movies, tags 데이터 정제 및 병합
- Spark 환경에서 전처리 파이프라인 실습 및 최적화

📍 관련 파일:
- `Preprocessing/preprocess/1203 Preproc-Spark.ipynb`
- `Preprocessing/preprocess/1113 PreProc.ipynb`

---

### 3) Recommendation Model Experiments
다양한 추천 알고리즘을 실험하고 비교했습니다.

#### (1) Collaborative Filtering (Item-based)
- 아이템 간 유사도를 기반으로 추천 점수 계산
- dot product 기반 추천 결과 추론

📍 관련 파일:
- `model/CF- Item-based_dot product_ASL + normal.ipynb`

#### (2) KNN 기반 추천
- 유사 사용자/유사 아이템 기반 추천 실험

📍 관련 파일:
- `model/ITEM_RATING_knn.ipynb`

#### (3) TF-IDF 기반 장르/텍스트 추천
- 장르/텍스트 데이터를 활용하여 유사 영화 추천

📍 관련 파일:
- `Preprocessing/preprocess/무비렌즈 데이터_genre_TFIDF.ipynb`

#### (4) Spark 기반 추천 모델 구현
- Spark 환경에서 추천 시스템 파이프라인 구현
- 대규모 데이터 처리 및 병렬 계산 기반 추천 결과 생성

📍 관련 파일:
- `model/Spark_Model.ipynb`
- `model/불Finda_Spark_movie_recommendation.ipynb`

---

## ▶️ How To Run

추천 실행을 위한 권장 실행 순서:

### 1. Dataset 준비
`dataset/` 폴더 내 MovieLens 파일 확인

### 2. Crawling 수행 (선택)
```bash
Preprocessing/crawling/
```

### 3. Preprocessing 수행
```bash
Preprocessing/preprocess/
```

### 4. 추천 모델 실행
```bash
model/
```

---

## 📌 Key Takeaways

- MovieLens 평점 데이터를 활용한 추천 시스템 구현 경험
- Spark 기반 데이터 병렬 처리 및 추천 파이프라인 구축 경험
- Item-based CF / KNN / TF-IDF 등 추천 알고리즘 비교 실험 수행
- 크롤링 기반 데이터 확장을 통해 추천 품질 개선 시도
- 추천 시스템의 End-to-End 구조를 직접 설계하며 실무 흐름 이해

---

## 🔥 Future Improvements

- Spark DataFrame 기반 리팩토링으로 성능 최적화
- ALS(Alternating Least Squares) 기반 Matrix Factorization 적용
- Precision@K, Recall@K, RMSE 기반 추천 품질 평가 자동화
- API 서버화(FastAPI) 및 배포 파이프라인 구성

---

## 📌 Notes

본 프로젝트는 학부 과정에서 추천 시스템 및 Spark 기반 데이터 처리를 학습하기 위해 진행된 팀 프로젝트입니다.  
Notebook 기반 실습 형태로 작성되었으며, 추천 파이프라인 설계 및 모델 실험 경험을 목적으로 진행되었습니다.
