# 사용법

```
docker rm [OPTIONS] CONTAINER_ID [CONTAINER...]
```

# 옵션

|   Option    | Short | Description                                 |
|:-----------:|:-----:| ------------------------------------------- |
|  `--force`  | `-f`  | 실행 중인 컨테이너 강제 제거 (SIGKILL 사용) |
|  `--link`   | `-l`  | 지정된 링크 제거                            |
| `--volumes` | `-v`  | 컨테이너와 관련된 익명 볼륨 제거            |
