---
layout: post
title: "Swift - 애플 개발자 문서 읽기"
tags: [스위프트, swift, ios, Apple Developer Doucument]
comments: true
---

부스트 코스에서 배운 내용을 토대로 작성하였습니다.

---

## 애플 문서 구성은 크게 3가지

* 참조 자료(API Reference)
> 클래스의 메서드와 프로퍼티에 대한 기술적인 세부사항에 관해 설명합니다.
* 가이드(Guide)
> 특정 분야에 대해 상세히 소개하고, 내부적으로 어떻게 구동되는지에 대해 설명합니다.<br>
  예상치 못한 정보를 많이 배울 수 있게 때문에 천천히 읽어보자!!
* 샘플 코드(Sample Code)
> 실제로 API를 어떻게 사용하는지에 대한 예시입니다. 예시는 봐서 나쁠게 하나도 없죠!


## 애플 문서 읽기 팁

1. 예를 들어 UILabel을 사용하는 경우,<br>
  [UILabel](https://developer.apple.com/documentation/uikit/uilabel) 참조 문서를 통해 기본적인 객체를 어떻게 생성, 사용할 수 있는지 살펴봅니다.
  
2. 레이블의 문자 색상/폰트/정렬 방법을 수정하고 싶다면 프로퍼티 부분을, 레이블 자체의 모양과 위치를 재정의 하고 싶다면 메서드 부분을 살펴봅니다.

3. 만약 원하는 프로퍼티나 메서드를 찾을 수 없다면 부모 클래스의 문서로 이동하여 원하는 기능을 찾아봅니다.

4. 레이블의 특정 이벤트가 발생하는 것을 감지하고 싶다면 델리게이트가 있는지 살펴보고, 있다면 해당 프로토콜 문서를 찾아가 살펴봅니다.

5. 원하는 기능이 **Deprecated**됐다면 다른 기능을 찾아 볼 수 밖에 없어요ㅠㅠ


##### 문서는 [애플 개발자 사이트](https://developer.apple.com/documentation/)나 Xcode 퀵헬프나 Xcode menu > Help > Developer Documentation을 찾아보면 됩니다. 


