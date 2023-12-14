[공식문서 참조](https://docs.docker.com/reference/)
# 정의

> 애플리케이션을 컨테이너화하여 개발, 배포 및 실행을 용이하게 하는 오픈 소스 플랫폼
> [[Dockerfile]]을 통해 [[Image]]를 만들고 이를 바탕으로 [[Container]]를 생성/실행하며, 데이터의 영속성을 위해 [[Volume]]을 활용

---
# 명령어

|        명령어        |                          설명                          |
|:--------------------:|:------------------------------------------------------:|
| **[[docker build]]** |  [[Dockerfile]]의 내용에 따라 도커의 [[Image]]를 생성  |
|  **[[docker run]]**  | [[Image]]기반으로 하나의 독립적인 [[Container]]를 만듬 |
|  **[[docker ps]]**   |    실행하고있는 [[Container]]의 목록과 정보를 조회     |
| **[[docker exec]]**  |          실행중인 [[Container]]에 명령을 실행          |
|  **[[docker rm]]**   |                  [[Container]]를 삭제                  |
|  **[[docker rmi]]**  |                    [[Image]]를 삭제                    |

