---
layout: post
title: "스위프트_2"
tags: [스위프트, swift, ios, class, struct, 값타입, 참조타입]
comments: true
---

야곰의 스위프트 기본 문법편을 바탕으로 작성하였습니다.

--- 

# 값타입과 참조타입

값타입과 참조타입을 공부하다 책의 내용이 이해하기 어려워 다시 정리하려 한다.<br>
내가 바보인거 같기도 하고..ㅎㅎ

### 우선 책의 내용은 이러했다.

> "구조체는 프로퍼티의 값을 변경하면 인스턴스 자체의 값도 함께 변경됩니다."<br>
"클래스 내부의 프로퍼티 값을 변경하더라도 할당된 메모리 주소에는 아무런 영향을 주지 않게 됩니다."

이 말을 이해하기 힘들어 천천히 정리해 보니 고개가 끄덕여 졌다.

## 정의부터 보자

### Class
  * 단일상속
  * 참조 타입
  * Apple 프레임워크의 대부분의 큰 뼈대를 구성
  
### Struct
  * 상속 불가
  * 값 타입
  * Swift의 대대분의 큰 뼈대는 모두 구조체로 구성
  
<br>
<br>

### 코드를 통해 보자면
<br>

```Swift
struct ValueType {
  var property = 1
}

let firstStructInstance = ValueType()
var secondStructInstance = firstStructInstance
secondStructInstance.property = 2

print("first struct instance property : \(firstStructInstance.property)")   // 1
print("second struct instance property : \(secondStructInstance.property)") // 2
```

구조체는 값에 의한 전달을 한다는 것을 보여주는 예제이다.<br>
상수(firstStructureInstance)에는 구조체 인스턴스를 할당하고 변수(secondStructureInstance)에는 위에서 만든 상수를 할당했다.
그리고 변수의 프로퍼티 값을 변경하였다.<br>
그 결과, 기존 인스턴스의 프로퍼티 값은 변함없이 1이 되고 변수로 선언한 구조체만 2로 변경이 되었다. 해석하면 기존에 선언했던 구조체가 복사되어 변수에 할당되었기 때문에 기존 구조체와 별개로 보고 프로퍼티 값이 변경되었다.

<br>
<br>

```Swift
class ReferenceType {
  var property = 1
}

let firstStructClassReference = ReferenceType()
var secondClassReference = firstClassReference
secondClassReference.property = 2

print("first class reference property : \(firstClassReference.porperty)")  // 2
print("second class reference property : \(secondClassReference.porperty)")  // 2
```

클래스는 주소에 의한 전달을 한다는 것을 보여주는 예제이다.<br>
변수로 선언한 인스턴스(secondClassReference)의 프로퍼티 값을 변경하면 first...와 second... 모두 한 클래스의 주소를 참조하기 때문에 둘 다 값이 바뀌는 것을 확인할 수 있다.


```Swift
struct Student {
  var name: String = "unknown"
  var subject: String = "Swift"
  
  // 인스턴스 메서드
  func Introduce() {
    print("저는 \(self.class)과목을 듣는 \(name)입니다.")
  }
}

var jangre: Student = Student()
jangre.name = "jangre"
jangre.class = "스위프트"
jangre.Introduce()  // 저는 스위프트과목을 듣는 jangre입니다.

let hyun: Student = Student()
//hyun.name = "hyun"  // 컴파일 오류 -> 불변 인스턴스이므로 프로퍼티 값 변경 불가
hyun.Introduce()  // 저는 Swift과목을 듣는 unknown입니다.
```
구조체의 경우, 변수로 선언된 인스턴스는 프로퍼티값을 변경할 수 있다. 하지만 상수로 선언된 인스턴스는 프로퍼티 값을 변경하면 값에 의한 전달로 인스턴스값도 변경되기 때문에 변경이 불가능하다.<br>
한 마디로 프로퍼티값을 변경하게 되면 인스턴스 자체의 값도 변경이 된다는 말이다.
<br>
<br>

```Swift
class Student {
  var name: String = "unknown"
  var subject: String = "Swift"
  
  // 인스턴스 메서드
  func Introduce() {
    print("저는 \(self.class)과목을 듣는 \(name)입니다.")
  }
}

var jangre: Student = Student()
jangre.name = "jangre"
jangre.class = "스위프트"
jangre.Introduce()  // 저는 스위프트과목을 듣는 jangre입니다.

let hyun: Student = Student()
hyun.name = "hyun"
hyun.Introduce()  // 저는 Swift과목을 듣는 hyun입니다.
```
하지만 클래스의 경우, 변수든 상수든 상관없이 프로퍼티값을 변경할 수 있다. 그 이유는 실제 저장된 메모리 주소에 의해 참조되어 프로퍼티 값이 바뀐다 해도 할당된 메모리 주소에는 영향을 주지 않기 때문에 변경이 가능하다.
