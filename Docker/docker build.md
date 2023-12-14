# 사용법

```
docker build [OPTIONS] PATH | URL | -
```

---
# 옵션

|         Option          | Short | Default | Description                                                        |
|:-----------------------:|:-----:|:-------:| ------------------------------------------------------------------ |
|       --add-host        |       |         | 사용자 지정 호스트-IP 매핑 추가 (host:ip)                          |
|       --build-arg       |       |         | 빌드 시 변수 설정                                                  |
|      --cache-from       |       |         | 캐시 소스로 고려할 이미지                                          |
|     --cgroup-parent     |       |         | 빌드 중 `RUN` 명령어에 대한 부모 cgroup 설정                       |
|       --compress        |       |         | 빌드 컨텍스트를 gzip으로 압축                                      |
|      --cpu-period       |       |         | CPU CFS (완전히 공정한 스케줄러) 주기 제한                         |
|       --cpu-quota       |       |         | CPU CFS (완전히 공정한 스케줄러) 할당량 제한                       |
|      --cpu-shares       |  -c   |         | CPU 공유 (상대적 가중치)                                           |
|      --cpuset-cpus      |       |         | 실행을 허용할 CPU 지정 (0-3, 0,1)                                  |
|      --cpuset-mems      |       |         | 실행을 허용할 MEM 지정 (0-3, 0,1)                                  |
| --disable-content-trust |       |  TRUE   | 이미지 검증 건너뛰기                                               |
|         --file          |  -f   |         | Dockerfile의 이름 (기본값은 `PATH/Dockerfile`)                     |
|       --force-rm        |       |         | 항상 중간 컨테이너 삭제                                            |
|        --iidfile        |       |         | 이미지 ID를 파일에 작성                                            |
|       --isolation       |       |         | 컨테이너 격리 기술                                                 |
|         --label         |       |         | 이미지의 메타데이터 설정                                           |
|        --memory         |  -m   |         | 메모리 제한                                                        |
|      --memory-swap      |       |         | 메모리와 스왑의 합과 같은 스왑 제한: 무제한 스왑을 활성화하려면 -1 |
|        --network        |       |         | API 1.25+ 빌드 중 `RUN` 명령어에 대한 네트워킹 모드 설정           |
|       --no-cache        |       |         | 이미지 빌드 시 캐시 사용하지 않기                                  |
|       --platform        |       |         | API 1.38+ 서버가 멀티 플랫폼 지원 가능한 경우 플랫폼 설정          |
|         --pull          |       |         | 항상 이미지의 새로운 버전을 가져오려고 시도                        |
|         --quiet         |  -q   |         | 빌드 출력 억제 및 성공 시 이미지 ID 출력                           |
|          --rm           |       |  TRUE   | 성공적인 빌드 후 중간 컨테이너 제거                                |
|     --security-opt      |       |         | 보안 옵션                                                          |
|       --shm-size        |       |         | `/dev/shm`의 크기                                                  |
|        --squash         |       |         | API 1.25+ 실험적 (데몬) 새로 빌드된 레이어를 단일 새 레이어로 압축 |
|          --tag          |  -t   |         | `이름:태그` 형식으로 이름과 선택적 태그 지정                       |
|        --target         |       |         | 빌드할 대상 빌드 단계 설정                                         |
|        --ulimit         |       |         | Ulimit 옵션                                                        |