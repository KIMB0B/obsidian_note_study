# 사용법

```
docker ps [OPTIONS]
```

# 옵션

| Option     | Short | Default | Description                                                                                                                                                                                                                                                                                                                                                                                                                               |
| ---------- | ----- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| --all      | -a    |         | Show all containers (default shows just running)                                                                                                                                                                                                                                                                                                                                                                                          |
| --filter   | -f    |         | Filter output based on conditions provided                                                                                                                                                                                                                                                                                                                                                                                                |
| --format   |       |         | [Format output using a custom template](https://docs.docker.com/go/formatting/)
| --last     | -n    | -1      | Show n last created containers (includes all states)                                                                                                                                                                                                                                                                                                                                                                                      |
| --latest   | -l    |         | Show the latest created container (includes all states)                                                                                                                                                                                                                                                                                                                                                                                   |
| --no-trunc |       |         | Don't truncate output                                                                                                                                                                                                                                                                                                                                                                                                                     |
| --quiet    | -q    |         | Only display container IDs                                                                                                                                                                                                                                                                                                                                                                                                                |
| --size     | -s    |         | Display total file sizes                                                                                                                                                                                                                                                                                                                                                                                                                  |

# 결과예시

| CONTAINER ID | IMAGE | COMMAND | CREATED | STATUS | PORTS | NAMES |
| ------------ | ----- | ------- | ------- | ------ | ----- | ----- |
|715ebfcee040|busybox|"top"|16 minutes ago|Up 16 minutes|8080/tcp|i_am_nostalgic|
|d5c976d3c462|busybox|"top"|23 minutes ago|Up 23 minutes|0.0.0.0:32768->80/tcp|top|
|9b6247364a03|busybox|"top"|24 minutes ago|Up 24 minutes|            |nostalgic_stallman|