## object(객체) & class 

1. object(객체)란?

   - 속성과 행위로 구성된 대상.

   - 변수와 함수의 묶음

   

2. class 선언

   1. 객체를 만들기 위해서는 클래스를 선언해야한다.  
      -  `class '키워드' ():` 키워드는 영대문자를 사용.
   2.  class 내 변수를 설정하고 `def 함수():` 형태로 함수 작성



3. object 초기화 (__init__)
   - `__init__()` : 객체 생성 및 속성값 지정 가능
   - init 지정해주면 객체를 생성하면서 속성을 지정할 수 있다. 

--------------------------------

### 클래스 변수 & 인스턴스 변수

- 클레스변수는 전반에 걸쳐 영향 
- 인스턴스 변수는 각 객체별로 영향



```python
class Car():
    instance_count = 0 
    
    def __init__(self, size, color):
        self.size = size
        self.color = color
        Car.instance_count = Car.instance_count + 1 #클래스 함수에 영향
        print("자동차 객체의 수: {0}".format(Car.instance_count))
    
    def move(self):
        print("자동차({0} &{1})가 움직입니다.".format(self.size, self.color))
       
    
car1 = Car('small', 'white') #객체 생성
car2 = Car('big', 'black')

print("Car 클레스의 총 인스턴스 갯수: {}".format(Car.instance_count)) #클래스 내 객체 갯수

car1.move() #인스턴스 함수에 영향
car2.move()
```





### instance method(인스턴스 메서드)

- 각 개체에서 개별적으로 동작하는 함수.

- 첫 인자로 `self` 가 필요하다. self는 객체 자신을 가르킨다.

  

  ```python
  class 클래스명():
      def 함수명(self[, 인자1, 인자2, ... 인자n]):
          self.변수명1 = 인자1
          self.변수명2 = 인자2
          self.변수명3 = 데이터
          ...
          
  ```

  ```python
  객체명 = 클래스명()
  객체명.메서드명([인자1, 인자2, ... , 인자n])
  ```

  Example

  ```python
  # 클레스 선언
  class Car():
      instance_count = 0
      
      def __init__(self, size, color):
          self.size = size #인스턴스 변수 생성 및 초기화
          self.color = color #인스턴스 변수 생성 및 초기화
          Car.instance_count = Car.instance_count + 1 #클레스 변수 사용
          print("자동차 객체의 수: {0}".format(Car.instance_count))
          
      #초기화 함수(인스턴스 메서드) 
      def move(self, speed):
          self.speed = speed # 인스턴스 변수 생성
          print("자동차({0}) & {1})가 ".format(self.size, self.color), end='')
          print("시속 {0} 킬로미터로 전진".format(self.speed))
          
      #인스턴스 메서드
      def auto_cruise(self):
          print("자율 주행 모드") 
          self.move(self.speed) # move() 함수의 인자로 인스턴스 변수를 입력
          
      
  ```

  ```python
  car1 = Car("small", "red") #객체 생성
  car2 = Car("big", "green") #객체 생성
  
  car1.move(80) #객체1 의 move() 메서드 호출
  car2.move(120) #객체2 의 move() 메서드 호출
  
  car1.auto_cruise() #객체1의 auto_cruise 메서드 호출
  car2.auto_cruise() #객체2의 auto_cruise 메서드 호출
  ```

  

### static method(정적 메서드)

- 객체와 관계없이 독립적으로 동작하는 함수를 만들 때 사용.

- class 내 함수와 별개로 작동한다.

- 함수 앞에 `@staticmethod`를 선언해서 메서드임을 표시
  
- ```python
  class 클래스명():
      @staticmethod
      def 함수명([인자1,2,...,n])
  ```



### class method(클래스 메서드)

- 클래스 변수를 사용하기 위한 함수.

- 함수를 정의할 때 첫 번째 인자로 클래스를 받는 cls가 필요하다.

- 함수 앞에 `@classmethod` 를 써야한다.

- ```python
  class 클래스명():
      @classmethod
      def 함수명(cls[,인자1,2,...,n])
  ```





### 클래스 상속

- 클래스에서 상속을 이용하면 이미 만들어진 클래스의 변수와 함수를 그대로 이용할 수 있어 코드의 재사용성이 좋아진다. 

- 공통부분을 부모 클래스로 구현, 각각 상속받는 식으로 코드를 짜면 편리하다.

- ```python
  class 자식 클래스 이름(부모 클래스 이름):
  ```

  
