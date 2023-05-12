# Code Peer Review Templete

- 코더 : 김형우
- 리뷰어 : 김태원

---

# PRT(PeerReviewTemplate)

각 항목을 스스로 확인하고 체크하고 확인하여 작성한 코드에 적용하세요.

- [x] 코드가 정상적으로 동작하고 주어진 문제를 해결했나요?
- [x] 주석을 보고 작성자의 코드가 이해되었나요?
- [] 코드가 에러를 유발할 가능성이 있나요?
- [x] 코드 작성자가 코드를 제대로 이해하고 작성했나요? (직접 인터뷰해보기)
- [x] 코드가 간결한가요?

---

   
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
 ```
   #출력 결과
   Using Comprehension:
   Nemo is swimming at 3 m/s
   Dory is swimming at 5 m/s
   Marlin is swimming at 7 m/s
   Bubbles is swimming at 2 m/s
   Gill is swimming at 4 m/s

   Using generator:
   <generator object show_fish_movement_generator at 0x7f7dfe50d4d0>
  ```

---
 ```
# 참고 링크 및 코드 개선 여부
리스트 컴프리헨션을 사용하여 print(),list,for문을 간결하게 축약하여 값을 출력했습니다.

show_fish_movement_generator(fish_list) 제너레이터 함수를 호출했을때 출력값이 주소가 나오는 이유는 '제너레이터 객체' 그 자체를 호출하였기 때문입니다.
필요한 과정은 제너레이터 객체에 '접근'하여 데이터를 추출해야 합니다.
올바른 결과값이 출력되려면 다음과 같은 과정이 필요합니다.
1.제너레이터 함수 정의                    ex) def show_fish_movement_generator(fish_list): yeild ....
2.제터레이터 객체 생성 및 할당            ex) gen = show_fish_movement_generator(fish_list)
3.제너레이터 객체의 이터레이터 생성       ex) for i in gen : print(....)   // for문을 통해 이터레이터 생성 및 출력
4.이터레이터 객체에 접근하여 데이터 출력
 ```

