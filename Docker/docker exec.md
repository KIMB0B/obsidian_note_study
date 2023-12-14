# 사용법

```
docker exec [OPTIONS] CONTAINER_ID COMMAND [ARG...]
```

# 옵션

| Option        | Short | Default | Description                                          |
| ------------- | ----- | ------- | ---------------------------------------------------- |
| --detach      | -d    |         | Detached mode: run command in the background         |
| --detach-keys |       |         | Override the key sequence for detaching a container  |
| --env         | -e    |         | API 1.25+ Set environment variables                  |
| --env-file    |       |         | API 1.25+ Read in a file of environment variables    |
| --interactive | -i    |         | Keep STDIN open even if not attached                 |
| --privileged  |       |         | Give extended privileges to the command              |
| --tty         | -t    |         | Allocate a pseudo-TTY                                |
| --user        | -u    |         | Username or UID (format: <name\|uid>[:<group\|gid>]) |
| --workdir     | -w    |         | API 1.35+ Working directory inside the container     |

# 사용 예시

```
// 715ebfcee040 컨테이너의 쉘을 사용
docker exec -it 715ebfcee040 /bin/bash
```