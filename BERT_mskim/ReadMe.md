# Pre-trained Model
`bert-base-multilingual-cased`

# Tokenizer
`BertTokenizer.from_pretrained("bert-base-multilingual-cased")`

---

## Directory tree
📦BERT_mskim
 ┣ 📂data
 ┃ ┣ 📜train_ai_last.csv
 ┃ ┣ 📜train_aug.csv
 ┃ ┣ 📜train_aug_old.csv
 ┃ ┣ 📜train_raw.csv
 ┃ ┗ 📜val.csv
 ┣ 📂ipynb
 ┃ ┣ 📜test1_naive.ipynb
 ┃ ┣ 📜test2_preprocess_sentence.ipynb
 ┃ ┣ 📜test3_preprocess_sentence2.ipynb
 ┃ ┣ 📜test4_all_train_data_augment.ipynb
 ┃ ┣ 📜test5_all_train_data_augment_stratify.ipynb
 ┃ ┣ 📜test6_80_per_train_data_augment_5.ipynb
 ┃ ┗ 📜test7_80_per_train_data_ai_preprocess.ipynb
 ┣ 📂submissions
 ┃ ┣ 📜submission_test1_naive.csv
 ┃ ┣ 📜submission_test2_preprocess_sentence.csv
 ┃ ┣ 📜submission_test3_preprocess_sentence2.csv
 ┃ ┣ 📜submission_test4_all_train_data_augment.csv
 ┃ ┣ 📜submission_test5_all_train_data_augment_stratify.csv
 ┃ ┣ 📜submission_test6_80_per_train_data_augment_5.csv
 ┃ ┗ 📜submission_test7_80_per_train_data_ai_preprocess.csv
 ┗ 📜ReadMe.md

---

### File Descriptions

1. 테스트 1
    - 요약
    > 데이터 전처리 없이 모델 훈련
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test1_naive.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_raw.csv`
    ---
    - 데이터 개수
    > 3950
    - 데이터 원본 정보
    > `/aiffel/aiffel/dktc/data/train.csv`
    - 훈련 데이터셋 정보
        - Train : Val 비율
        > `8:2`
        - 모듈 정보
        > `from sklearn.model_selection import train_test_split`
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `LEARNING_RATE`: 1e-5
        - `EPOCH`: 3
    ---
    - 모델 평가
        - `loss`: `0.5592`
        - `accuracy`: `0.8203`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test1_naive.csv`

2. 테스트 2
    - 요약
    > 데이터 전처리 후 모델 훈련
    >> `preprocess_sentence()` 함수 선언 후 사용
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test2_preprocess_sentence.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_raw.csv`
    ---
    - 데이터 개수
    > 3950
    - 데이터 원본 정보
    > `/aiffel/aiffel/dktc/data/train.csv`
    - 훈련 데이터셋 정보
        - Train : Val 비율
        > `8:2`
        - 모듈 정보
        > `from sklearn.model_selection import train_test_split`
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 1e-5
        - `EPOCH`: 3
    ---
    - 모델 평가
        - `loss`: `0.5386`
        - `accuracy`: `0.8266`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test2_preprocess_sentence.csv`

3. 테스트 3
    - 요약
    > 데이터 전처리 후 모델 훈련
    >> `preprocess_sentence2()` 함수 선언 후 사용
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test3_preprocess_sentence2.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_raw.csv`
    ---
    - 데이터 개수
    > 3950
    - 데이터 원본 정보
    > `/aiffel/aiffel/dktc/data/train.csv`
    - 훈련 데이터셋 정보
        - Train : Val 비율
        > `8:2`
        - 모듈 정보
        > `from sklearn.model_selection import train_test_split`
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 1e-5
        - `EPOCH`: 3
    ---
    - 모델 평가
        - `loss`: `0.5236`
        - `accuracy`: `0.8405`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test3_preprocess_sentence2.csv`

4. 테스트 4
    - 요약
    > 데이터 증강(`Augment`) 후 모델 학습
    >> 원본 데이터(same as `train_raw.csv`) 전체를 5배로 증강한 데이터를 사용
    >>> 데이터는 기본적인 전처리가 되어있음 (`from soynlp.normalizer import *` 작업이 된 데이터)
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test4_all_train_data_augment.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_aug_old.csv`
    ---
    - 데이터 개수
    > 19750
    - 데이터 원본 정보
    > `/aiffel/aiffel/train_aug_old.csv`
    - 훈련 데이터셋 정보
        - Train : Val 비율
        > `8:2`
        - 모듈 정보
        > `from sklearn.model_selection import train_test_split`
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 1e-5
        - `EPOCH`: 3
    ---
    - 모델 평가
        - `loss`: `0.0658`
        - `accuracy`: `0.9828`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test4_all_train_data_augment.csv`

5. 테스트 5
    - 요약
    > 데이터 증강(`Augment`) 후 모델 학습
    >> 원본 데이터(same as `train_raw.csv`) 전체를 5배로 증강한 데이터를 사용
    >>> 데이터는 기본적인 전처리가 되어있음 (`from soynlp.normalizer import *` 작업이 된 데이터)
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test5_all_train_data_augment_stratify.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_aug_old.csv`
    ---
    - 데이터 개수
    > 19750
    - 데이터 원본 정보
    > `/aiffel/aiffel/train_aug_old.csv`
    - 훈련 데이터셋 정보
        - Train : Val 비율
        > `8:2`
        - 모듈 정보
        > `from sklearn.model_selection import train_test_split`
        >> 데이터 분류(`train`, `val`) 시 클래스별 균등 분배 옵션 부여 (`stratify=train_data['class']`)
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 2e-5
        - `EPOCH`: 10
    ---
    - 모델 평가
        - `loss`: `0.0559`
        - `accuracy`: `0.9851`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test5_all_train_data_augment_stratify.csv`

6. 테스트 6
    - 요약
    > 원본 데이터(same as `train_raw.csv`)를 `8:2` 비율로 분리
    >> `2`비율로 나누어진 데이터를 `val.csv`로 생성 &rarr; Validation 데이터로 사용
    >>> `8`비율의 데이터를 5배수로 증강하여 `train_aug.csv`로 생성 &rarr; Train 데이터로 사용
    >>>> 데이터는 기본적인 전처리가 되어있음 (`from soynlp.normalizer import *` 작업이 된 데이터)
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test6_80_per_train_data_augment_5.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_aug.csv`
    ---
    - 데이터 개수
    > 15800, 790 &rarr; train, validation
    - 데이터 원본 정보
    > `/aiffel/aiffel/train_aug.csv`, `/aiffel/aiffel/val.csv`
    - 훈련 데이터셋 정보
        - Train
        > `train_aug.csv`
        >> DKTC 훈련데이터에서 `80%`를 가져온 후, 5배 증강시킨 데이터
        - Validaion
        > `val.csv`
        >> DKTC 훈련데이터에서 `20%`를 가져온 데이터
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 2e-5
        - `EPOCH`: 6
    ---
    - 모델 평가
        - `loss`: `0.8031`
        - `accuracy`: `0.8392`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test6_80_per_train_data_augment_5.csv`

7. 테스트 7
    - 요약
    > 원본 데이터(same as `train_raw.csv`)를 `8:2` 비율로 분리
    >> `2`비율로 나누어진 데이터를 `val.csv`로 생성 &rarr; Validation 데이터로 사용
    >>> `8`비율의 데이터를 `CHAT GPT`로 전처리하여 `train_ai_last.csv`로 생성 &rarr; Train 데이터로 사용
    >>>> `train.csv`의 경우 가해자와 피해자 대화가 합쳐진 텍스트 문장들이 저장되어있다.
    >>>>> 가해자의 텍스트만을 추출하여 파일(`train_ai_last.csv`)을 만들었다.
    - Jupyter 파일 정보
    > `BERT_mskim/ipynb/test6_80_per_train_data_augment_5.ipynb`
    - 사용 데이터 정보
    > `BERT_mskim/data/train_aug.csv`
    ---
    - 데이터 개수
    > 15800, 790 &rarr; train, validation
    - 데이터 원본 정보
    > `/aiffel/aiffel/train_aug.csv`, `/aiffel/aiffel/val.csv`
    - 훈련 데이터셋 정보
        - Train
        > `train_ai_last.csv`
        >> DKTC 훈련데이터에서 `80%`를 가져온 후, CHAT GPT로 가해자 텍스트만 전처리하여 데이터를 가공
        - Validaion
        > `val.csv`
        >> DKTC 훈련데이터에서 `20%`를 가져온 데이터
    ---
    - 모델 파라미터
        - `MAX_LEN`: 128
        - `BATCH_SIZE`: 16
        - `lr`: 1e-5
        - `EPOCH`: 6
    ---
    - 모델 평가
        - `loss`: `0.3053`
        - `accuracy`: `0.9076`
    ---
    - `SUBMISSION` 파일 정보
    > `BERT_mskim/submissions/submission_test6_80_per_train_data_augment_5.csv`

