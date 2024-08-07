gensim - Word2Vec 라이브러리 사용하여, 기본적인 모델의 훈련 방식 학습   

# train_ENG.py
.xml 형식의 데이터셋 사용 (https://raw.githubusercontent.com/ukairia777/tensorflow-nlp-tutorial/main/09.%20Word%20Embedding/dataset/ted_en-20160408.xml)

### Pre-processing Step
* \<head>, \<url>, ... 등 제외한 , \<content>의 내용 추출
* (Laughter), (Applause), ... 배경음을 의미하는 단어 제거
* 문장 토큰화
* 구두점 제거
* 대문자 -> 소문자
* 각 문장별 단어 토큰화   


# train_KOR.py
.txt 형식의 네이버 영화 리뷰 데이터셋 사용 (https://raw.githubusercontent.com/e9t/nsmc/master/ratings.txt)

### Pre-processing
* NULL 제거
* 토큰화
* 학습에 사용하지 않으려는 단어 제거 <- 사용자 정의
     - 한글이 아닌 경우
     - ['의','가','이','은','들','는','좀','잘','걍','과','도','를','으로','자','에','와','한','하다']


# train_negative_sampling.py
sklearn의 데이터셋 사용 (from sklearn.datasets import fetch_20newsgroups)  
negative sampling 방식을 이용한 word2vec (skip-gram 방식)   
    

### Pre-processing : negative sampling 방식에 맞게 데이터셋 수정
* 특수 문자 제거
* 길이가 짧은 단어 제거 (길이 <= 3으로 지정)
* 소문자화
* empty 값, NULL값 제거
* 학습에 사용하지 않으려는 단어 제거 = NLTK에서 정의한 불용어 리스트 활용
* 각 문장에 포함된 단어의 개수가 적은 경우, 문장 제거 (단어 개수 <= 1로 지정)
