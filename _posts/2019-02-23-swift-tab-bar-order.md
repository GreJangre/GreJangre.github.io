---
layout: post
title: "Swift - 탭바 레이아웃 순서 찾기"
tags: [스위프트, swift, ios, Tab Bar, Controller]
comments: true
---

탭바를 구성할 때 순서가 꼬여 어떤 뷰가 먼저인지 헷갈릴 수 있다.

--- 

# 탭뷰 순서 찾아내기

소소한 팁이지만 뷰의 순서를 찾는 아주 간단한 방법을 소개한다.

![2019-02-23 5 19 03](https://user-images.githubusercontent.com/25144780/53283812-3628b800-378f-11e9-8909-a1d3a1df5cf5.png)

> 탭바 컨트롤러 씬 부분을 보면 세그웨이에 대한 정보를 표현하고 있다.

![2019-02-23 5 10 05](https://user-images.githubusercontent.com/25144780/53283854-8e5fba00-378f-11e9-856c-8aa87accfc4c.png)

> 세그웨이 정보를 클릭하면 화면에서 보듯이 컨트롤러와 뷰가 연결된 라인의 색이 변했다.
  해당 뷰가 탭 바의 첫 번째 아이템에 해당한다.
  
![2019-02-23 5 10 13](https://user-images.githubusercontent.com/25144780/53283902-0af29880-3790-11e9-8c50-761fb4513c41.png)

> 2번째 세그웨이를 클릭하면 2번째 아이템과 연결된 뷰의 라인이 부각된다!!

<br>
<br>
### 정말 소소한 팁이지만 혹시나 헤매고 있는 사람들에게 조금이나 도움이 됐길..!  