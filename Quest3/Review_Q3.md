# Code Peer Review Templete
- 코더 : 김형우
- 리뷰어 : 김태원


# PRT(PeerReviewTemplate)
각 항목을 스스로 확인하고 체크하고 확인하여 작성한 코드에 적용하세요.
- [x] 1.코드가 정상적으로 동작하나요?
- [x] 2.문제를 제대로 이해했나요?
- [x] 3.함수가 작동하는 방식을 잘 설명했나요?
- [ ] 4.발생 가능한 에러를 찾아서 디버깅을 했나요?
- [ ] 5.코드를 더 개선시켰나요?



'''python
from google.colab import drive
drive.mount('/content/drive')


with open('/content/drive/MyDrive/06TheAvengers.txt', 'r') as f:
  text = f.read()
print(text)

# f = open("/gdrive/My drive/06TheAvengers.txt", 'r')
# lines = f.readlines()
# f.close()
        
# for line in lines:
#   print(line)    # 파일 불러오는 코드

# text = f

# Avenger = Avengers.lower().split()         # 소문자로 변경해주기, 스플릿 해서 

# Avengers = text.split() # 
# max2gram = Avengers() # 가장 많은 빈도의 두 단어 출력 

# if(len())

# print(max2gram, countdict[max2gram])
# print(Counter(baglist))
'''

# 참고 링크 및 코드 개선 여부
- 코랩 드라이브에서 txt 파일을 불러오기 까지 성공한 단계입니다.
- 소문자 변환, 공백 나누기, 단어 개수 카운트 작성 과정이 보입니다. 하지만 미완성이라 오류가 발생합니다.
