# Code Peer Review Templete

- 코더 : 김형우
- 리뷰어 : 김태원

---

# PRT(PeerReviewTemplate)

각 항목을 스스로 확인하고 체크하고 확인하여 작성한 코드에 적용하세요.

- [x] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
- [ ] 주석을 보고 작성자의 코드가 이해되었나요?
- [ ] 코드가 에러를 유발할 가능성이 있나요?
- [ ] 코드 작성자가 코드를 제대로 이해하고 작성했나요? (직접 인터뷰해보기)
- [ ] 코드가 간결한가요?

---

# 예시

1. 코드의 작동 방식을 주석으로 기록합니다.

2. 코드의 작동 방식에 대한 개선 방법을 주석으로 기록합니다.

3. 참고한 링크 및 ChatGPT 프롬프트 명령어가 있다면 주석으로 남겨주세요.
   
   ```python
      class Fish:
    def __init__(self, name, speed): # fish 클래스를 정의, 이름과 속력을 줌
        self.name = name
        self.speed = speed
  
    # def __repr__(self): # 물고기 속도 깔끔하게 하려고 해주는 함수 정의, 사용자가 객체 자체를 이해할 수 있게 표현해주는 메서드
    #     return '{}{}'.format(fish_list)
    
   def show_fish_movement_comprehension(fish_list):
    [print(f'{fish.name} is swimming at {fish.speed} m/s')for fish in fish_list] # 컴프리헨션으로 구현
    
   # def show_fish_movement_iterator(fish_list):
   #     fish_iter = iter(fish_list)
   #     
   #     print(f'(is swimming at ))m/s' # 이터레이터로 구현 이터러블 객체를 넣어서 해보자인데 제너레이터만 구현하기

   def show_fish_movement_generator(fish_list):
        for fish in fish_list:
            yield f'{fish.name} is swimming at {fish.speed} m/s \n'# 제너레이터로 구현: 제너레이터 주소 값을 입력 값으로 출력해주기
            #밑의 코드대로 동작하려면 return 값을 줘야 하는가?

   fish_list = [
       Fish("Nemo", 3),
       Fish("Dory", 5),
       Fish("Marlin", 7),
       Fish("Bubbles", 2),
       Fish("Gill", 4)
   ]

   # 물고기들의 움직임 출력
   print("Using Comprehension:")
   show_fish_movement_comprehension(fish_list)

   print("\nUsing generator:")
   show_fish_movement_generator(fish_list)
   # print(*show_fish_movement_generator(fish_list)) # 출력하면 컴프리헨션과 똑같이 나와주지만 위의 코드만 이용해서 출력하게 해야한다면 사용 불가
 ```
   
   - Code 에 대한 리뷰어의 Comment 를 남겨주세요

---

# 참고 링크 및 코드 개선 여부

```python
#
#
#
#
```
