# AIFFEL Campus Online 4th Code Peer Review Templete
- 코더 : .
- 리뷰어 : 본인의 이름을 작성하세요.

# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 토의하여 작성한 코드에 적용합니다.
- [x] 1.코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
- [O] 2.주석을 보고 작성자의 코드가 이해되었나요?
  > 
- [O] 3.코드가 에러를 유발할 가능성이 있나요?
  > vocab이 빈도수를 계산해서 입력한게 아니라서 , 조정 하셔야 할것
  > 같습니다.
- [X] 4.코드 작성자가 코드를 제대로 이해하고 작성했나요?
  > 옙.
- [O] 5.코드가 간결한가요?
  > 위 항목에 대한 근거 작성 필수

# 예시
1. 일부만 올리겠습니다. 
```python

threshold = 7
total_cnt = len(src_tokenizer.word_index) # 단어의 수
rare_cnt = 0 # 등장 빈도수가 threshold보다 작은 단어의 개수를 카운트
total_freq = 0 # 훈련 데이터의 전체 단어 빈도수 총 합
rare_freq = 0 # 등장 빈도수가 threshold보다 작은 단어의 등장 빈도수의 총 합

# 단어와 빈도수의 쌍(pair)을 key와 value로 받는다.
for key, value in src_tokenizer.word_counts.items():
    total_freq = total_freq + value

    # 단어의 등장 빈도수가 threshold보다 작으면
    if(value < threshold):
        rare_cnt = rare_cnt + 1
        rare_freq = rare_freq + value

print('단어 집합(vocabulary)의 크기 :',total_cnt)
print('등장 빈도가 %s번 이하인 희귀 단어의 수: %s'%(threshold - 1, rare_cnt))
print('단어 집합에서 희귀 단어를 제외시킬 경우의 단어 집합의 크기 %s'%(total_cnt - rare_cnt))
print("단어 집합에서 희귀 단어의 비율:", (rare_cnt / total_cnt)*100)
print("전체 등장 빈도에서 희귀 단어 등장 빈도 비율:", (rare_freq / total_freq)*100)
     
단어 집합(vocabulary)의 크기 : 42490
등장 빈도가 6번 이하인 희귀 단어의 수: 30761
단어 집합에서 희귀 단어를 제외시킬 경우의 단어 집합의 크기 11729
단어 집합에서 희귀 단어의 비율: 72.39585784890562
전체 등장 빈도에서 희귀 단어 등장 빈도 비율: 8.297034519481715

#srv vocab 은 희귀 단어를 제외시킬 경우의 단어 집합을 기준으로 잡아주셔야 합니다.
#아래와 같이 수정 해주시면 좋을것 같습니다.!!
#src_vocab = 11700
#src_tokenizer = Tokenizer(num_words = src_vocab) # 단어 집합의 크기를 11,700으로 제한
#src_tokenizer.fit_on_texts(encoder_input_train) # 단어 집합 재생성

src_vocab = 8000
src_tokenizer = Tokenizer(num_words = src_vocab) # 단어 집합의 크기를 8,000으로 제한
src_tokenizer.fit_on_texts(encoder_input_train) # 단어 집합 재생성.
     


```

# 참고 링크 및 코드 개선
```python
# 노드 기준으로 작성하셔서 , 눈에 띄게 수정할 부분이 보이지는 않습니다.!! 고생 하셨습니다!!!!
```
