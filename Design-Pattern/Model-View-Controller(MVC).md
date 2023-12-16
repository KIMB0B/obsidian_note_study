# 정의

> 하나의 애플리케이션, 프로젝트를 구성할 때 그 구성요소를 세가지의 역할로 구분한 패턴.
> 그 세개가 Model, View, Controller

---
# 구성

![[Pasted image 20231217014241.png]]
- `controllers` : 미들웨어 함수를 분리해서 관리해 줄 곳
- `models` : DB 생성을 관리해주는 곳
- `view` : 화면에 보여지는 파일들(html 파일)을 관리해주는 곳

---
# 실행 과정

1. controller를 조작
2. controller는 model을 통해서 데이터를 가져옴
3. 그 정보를 바탕으로 시각적인 표현을 담당하는 View를 제어해서 사용자에게 전달

---
# 예시

[[MVC 예시]]
![[Pasted image 20231217024045.png]]