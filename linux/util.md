File Count(`ls`) 
```bash
# 파일 개수 확인
ls -l | grep ^- | wc -l

# symbolic link
ln -s [target path] [source path]
```
`hostname`
```
hostname -s 127.0.0.1 
```
디스크 용량 확인(`df`)
```
$ df -l # limit listing to local file systems
$ df . # pwd 사용 가능 공간 확인 
$ df -h # print sizes in human readable format (defulat : GB)
```

파이프라인 사용 시 변수 지정(`xargs`) 
