# 사용법

```
docker ps [OPTIONS]
```

---
# 옵션

|   Option   | Short | Default | Description                                                                            |
|:----------:|:-----:|:-------:| -------------------------------------------------------------------------------------- |
|   --all    |  -a   |         | 모든 컨테이너 표시 (기본값은 실행 중인 컨테이너만 표시)                                |
|  --filter  |  -f   |         | 제공된 조건에 따라 출력 필터링                                                         |
|  --format  |       |         | [사용자 정의 템플릿을 사용하여 출력 형식 지정](https://docs.docker.com/go/formatting/) |
|   --last   |  -n   |   -1    | 마지막으로 생성된 n개의 컨테이너 표시 (모든 상태 포함)                                 |
|  --latest  |  -l   |         | 가장 최근에 생성된 컨테이너 표시 (모든 상태 포함)                                      |
| --no-trunc |       |         | 출력을 줄이지 않음                                                                     |
|  --quiet   |  -q   |         | 컨테이너 ID만 표시                                                                     |
|   --size   |  -s   |         | 전체 파일 크기 표시                                                                    |

---
# 결과예시

| CONTAINER ID | IMAGE | COMMAND | CREATED | STATUS | PORTS | NAMES |
| ------------ | ----- | ------- | ------- | ------ | ----- | ----- |
|715ebfcee040|busybox|"top"|16 minutes ago|Up 16 minutes|8080/tcp|i_am_nostalgic|
|d5c976d3c462|busybox|"top"|23 minutes ago|Up 23 minutes|0.0.0.0:32768->80/tcp|top|
|9b6247364a03|busybox|"top"|24 minutes ago|Up 24 minutes|            |nostalgic_stallman|