# 사용법

```
docker exec [OPTIONS] CONTAINER_ID COMMAND [ARG...]
```

---
# 옵션

|    Option     | Short | Description                                             |
|:-------------:|:-----:| ------------------------------------------------------- |
|   --detach    |  -d   | 분리 모드: 백그라운드에서 명령어 실행                   |
| --detach-keys |       | 컨테이너 분리 시 키 시퀀스 재정의                       |
|     --env     |  -e   | API 1.25+ 환경 변수 설정                                |
|  --env-file   |       | API 1.25+ 환경 변수 파일 읽기                           |
| --interactive |  -i   | 연결되어 있지 않아도 STDIN을 열어두기                   |
| --privileged  |       | 명령어에 확장된 권한 부여                               |
|     --tty     |  -t   | 가상 TTY 할당                                           |
|    --user     |  -u   | 사용자 이름 또는 UID (형식: <name\|uid>[:<group\|gid>]) |
|   --workdir   |  -w   | API 1.35+ 컨테이너 내 작업 디렉토리                     |

---
# 사용 예시

```
// 715ebfcee040 컨테이너의 쉘을 사용
docker exec -it 715ebfcee040 /bin/bash
```