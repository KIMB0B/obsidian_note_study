# 정의

> 여러 개의 [[Image]]를 실행시키는 [[Container]]를 만들기 위한 [[Docker]] 기능
> [[Name Resolution]]을 통해 각 [[Container]]끼리의 연결을 편하게 해줌

---
# 사용법

여러 [[Dockerfile]]을 한번에 정의하는 docker-compose.yaml을 만들면 사용 가능

---
# docker-compose 작성 예시
```yaml
version: '3.7'

# 컴퓨터들
services:

  # 컴퓨터이름
  my-backend:
    build:
      context: .
      dockerfile: Dockerfile
    volumes:
      - ./index.js:/myfolder/index.js
      - ./email.js:/myfolder/email.js
    ports:
      - 4000:4000


  # 컴퓨터이름
  my-database:
    image: mongo:latest
    ports:
      - 27017:27017
```