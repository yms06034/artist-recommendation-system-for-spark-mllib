
# Spark_ML (ALS Model)
artist recommendation system for spark mllib

## Description
Spark Mllib를 활용해 Music Artist Recommendation System을 구축 하였습니다.
### DATA
[Music Listening Dataset](https://last.fm/) 사용
- user_artist_data.txt
	- 3 columns: userid artistid playcount
- artist_data.txt
	- 2 columns: artistid artist_name
- artist_alias.txt
	- 2 columns: badid goodid

### PROCESS
EC2 환경에서 진행 하였으며, 단일 서버로 구축하여 Spark를 활용하였습니다. \
먼저 HDFS에 데이터를 업로드 후 데이터 분석 및 전처리를 진행해 주었습니다. \
이후 Cassandra에 최종 데이터를 담아 주었고, ALS 모델을 활용해 학습해 주었습니다. \
RMSE로 평가 진행 후 CrossValidator 등을 진행 한 후 Best Model을 추출하여 HDFS에 저장해 주었습니다. \
최종적으로 추천 된 내용을 Redis에 담아 주었습니다.

### PIPELINE

![spark_ML_pipeline](https://user-images.githubusercontent.com/98085184/231084137-dbeca82a-8d46-40c8-a03e-2a8abe484c54.png)

### RETROSPECTIVE
