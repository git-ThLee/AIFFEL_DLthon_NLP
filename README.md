# DLthon 프로젝트

> DLthon 이란 아이펠에서 진행하는 DL(딥러닝) 과 thon(마라톤)을 합친 용어입니다.


# DKTC

본 프로젝트의 주제는 DKTC (Dataset of Korean Threatening Conversations)입니다. 자세한 설명은 [원본](https://github.com/tunib-ai/DKTC)에서 확인이 가능합니다.

## 과제 

1. DKTC 훈련 데이터를 이용해
`협박`, `갈취`, `직장 내 괴롭힘`, `기타 괴롭힘` 4가지 대화 유형 Class를 분류하는 딥러닝 모델을 만듭니다.
2. DKTC 테스트 데이터를 활용해 분류 성능을 평가합니다.

## 멤버 

| 이름  | 깃허브 | 담당 |
|:---:|:---:|:---:|
|손정민| [깃헙](https://github.com/rurube)| 데이터 분석 ,  데이터 증강 |
|김민식| [깃헙](minsigi8911@gmail.com)| 모델링(BERT_Multilingual-cased) |
|김석영| [깃헙](saiitmail@gmail.com)| 모델링(KLUE,Transformer Encoder) |
|이태훈| [깃헙](https://github.com/git-ThLee)| 데이터 분석 , GPT 전처리 |


## 세부 일정

| Day | 날짜 | 활동 |
|:---:|:---:|:---:|
|1| 23.08.29(화) | 주제공개,팀 빌딩,팀장 선정,DLthon 진행|
|2| 23.08.30(수) | DLthon 진행|
|3| 23.08.31(목) | 발표 |

---

## 성능

- Acc : 0.91 


## 모델

1. KLUE
2. Ko-Bert

## 모델 분석

![Alt text](image.png)

## 성능 향상 시도

> Augmentation

![Alt text](image-1.png)

> 문장 선별(가해자 텍스트만 추출) + OpenAI API 활용

![Alt text](image-2.png)

## 성능

![Alt text](image-3.png)

---

자세한 내용은 pptx에서도 확인이 가능합니다.