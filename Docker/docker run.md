# 사용법

```
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

# 옵션

|Option|Short|Default|Description|
|---|---|---|---|
|--add-host|||사용자 지정 호스트-IP 매핑 추가 (host:ip)|
|--annotation|||API 1.43+ 컨테이너에 주석 추가 (OCI 런타임으로 전달됨)|
|--attach|-a||STDIN, STDOUT 또는 STDERR에 연결|
|--blkio-weight|||블록 IO (상대적 가중치), 10에서 1000 사이, 또는 0으로 비활성화 (기본값 0)|
|--blkio-weight-device|||블록 IO 가중치 (상대적 장치 가중치)|
|--cap-add|||리눅스 기능 추가|
|--cap-drop|||리눅스 기능 삭제|
|--cgroup-parent|||컨테이너에 대한 선택적 부모 cgroup|
|--cgroupns|||API 1.41+ 사용할 Cgroup 네임스페이스 (host\|private) 'host': 컨테이너를 도커 호스트의 cgroup 네임스페이스에서 실행 'private': 컨테이너를 자체 개인 cgroup 네임스페이스에서 실행 '': 데몬의 default-cgroupns-mode 옵션에 의해 구성된 cgroup 네임스페이스 사용 (기본값)|
|--cidfile|||컨테이너 ID를 파일에 작성|
|--cpu-count|||CPU 수 (윈도우 전용)|
|--cpu-percent|||CPU 퍼센트 (윈도우 전용)|
|--cpu-period|||CPU CFS (완전히 공정한 스케줄러) 주기 제한|
|--cpu-quota|||CPU CFS (완전히 공정한 스케줄러) 할당량 제한|
|--cpu-rt-period|||API 1.25+ 마이크로초 단위로 CPU 실시간 주기 제한|
|--cpu-rt-runtime|||API 1.25+ 마이크로초 단위로 CPU 실시간 런타임 제한|
|--cpu-shares|-c||CPU 공유 (상대적 가중치)|
|--cpus|||API 1.25+ CPU 수|
|--cpuset-cpus|||실행을 허용할 CPU (예: 0-3, 0,1)|
|--cpuset-mems|||실행을 허용할 메모리 (예: 0-3, 0,1)|
|--detach|-d||백그라운드에서 컨테이너를 실행하고 컨테이너 ID 출력|
|--detach-keys|||컨테이너 분리를 위한 키 시퀀스 재정의|
|--device|||호스트 장치를 컨테이너에 추가|
|--device-cgroup-rule|||cgroup 허용 장치 목록에 규칙 추가|
|--device-read-bps|||장치에서 읽기 속도 제한 (초당 바이트)|
|--device-read-iops|||장치에서 읽기 속도 제한 (초당 IO)|
|--device-write-bps|||장치로의 쓰기 속도 제한 (초당 바이트)|
|--device-write-iops|||장치로의 쓰기 속도 제한 (초당 IO)|
|--disable-content-trust||TRUE|이미지 검증 건너뛰기|
|--dns|||사용자 지정 DNS 서버 설정|
|--dns-opt|||DNS 옵션 설정|
|--dns-option|||DNS 옵션 설정|
|--dns-search|||사용자 지정 DNS 검색 도메인 설정|
|--domainname|||컨테이너 NIS 도메인 이름|
|--entrypoint|||이미지의 기본 ENTRYPOINT 덮어쓰기|
|--env|-e||환경 변수 설정|
|--env-file|||환경 변수 파일 읽기|
|--expose|||포트 또는 포트 범위 노출|
|--gpus|||API 1.40+ 컨테이너에 추가할 GPU 장치 ('all'로 모든 GPU 전달)|
|--group-add|||추가 그룹 참여|
|--health-cmd|||건강 상태 확인을 위한 명령어 실행|
|--health-interval|||건강 상태 확인 사이의 시간 (ms\|s\|m\|h) (기본값 0s)|
|--health-retries|||건강하지 않음을 보고하기 위한 연속 실패 횟수|
|--health-start-period|||API 1.29+ 건강 상태 재시도 카운트다운을 시작하기 전 컨테이너 초기화 기간 (ms\|s\|m\|h) (기본값 0s)|
|--health-timeout|||한 번의 확인을 실행할 수 있는 최대 시간 (ms\|s\|m\|h) (기본값 0s)|
|--help|||사용법 출력|
|--hostname|-h||컨테이너 호스트 이름|
|--init|||API 1.25+ 컨테이너 내에서 신호를 전달하고 프로세스를 정리하는 init 실행|
|--interactive|-i||연결되지 않아도 STDIN을 열어두기|
|--io-maxbandwidth|||시스템 드라이브의 최대 IO 대역폭 제한 (윈도우 전용)|
|--io-maxiops|||시스템 드라이브의 최대 IOps 제한 (윈도우 전용)|
|--ip|||IPv4 주소 (예: 172.30.100.104)|
|0|||IPv6 주소 (예: 2001:db8::33)|
|--ipc|||사용할 IPC 모드|
|--isolation|||컨테이너 격리 기술|
|--kernel-memory|||커널 메모리 제한|
|--label|-l||컨테이너에 메타데이터 설정|
|--label-file|||라벨이 있는 줄 단위 파일 읽기|
|--link|||다른 컨테이너에 링크 추가|
|--link-local-ip|||컨테이너 IPv4/IPv6 링크 로컬 주소|
|--log-driver|||컨테이너의 로깅 드라이버|
|--log-opt|||로그 드라이버 옵션|
|--mac-address|||컨테이너 MAC 주소 (예: 92:d0:c6:0a:29:33)|
|--memory|-m||메모리 제한|
|--memory-reservation|||메모리 소프트 제한|
|--memory-swap|||메모리와 스왑의 합과 같은 스왑 제한: '-1'로 무제한 스왑 활성화|
|--memory-swappiness||-1|컨테이너 메모리 swappiness 조정 (0에서 100)|
|--mount|||컨테이너에 파일시스템 마운트 연결|
|--name|||컨테이너에 이름 할당|
|--net|||컨테이너를 네트워크에 연결|
|--net-alias|||컨테이너에 네트워크 범위 별칭 추가|
|--network|||컨테이너를 네트워크에 연결|
|--network-alias|||컨테이너에 네트워크 범위 별칭 추가|
|--no-healthcheck|||컨테이너에 지정된 HEALTHCHECK 비활성화|
|--oom-kill-disable|||OOM 킬러 비활성화|
|--oom-score-adj|||호스트의 OOM 선호도 조정 (-1000에서 1000)|
|--pid|||사용할 PID 네임스페이스|
|--pids-limit|||컨테이너 PID 제한 조정 (무제한으로 설정하려면 -1)|
|--platform|||API 1.32+ 서버가 멀티 플랫폼 지원 가능한 경우 플랫폼 설정|
|--privileged|||이 컨테이너에 확장된 권한 부여|
|--publish|-p||컨테이너의 포트(들)를 호스트에 공개|
|--publish-all|-P||모든 노출된 포트를 무작위 포트로 공개|
|--pull||missing|실행 전 이미지 가져오기 (항상, 없음, 절대 안 함)|
|--quiet|-q||가져오기 출력 억제|