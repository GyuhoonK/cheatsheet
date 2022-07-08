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

압축풀기 및 라이브러리 
```bash
# Apache Tomcat을 다운받은 경로에서 /usr/local 경로로 압축 해제
sudo tar -xzvf apache-tomcat-8.5.65.tar.gz -C /usr/local/apache-tomcat-8.5.65

# Library 경로에 Tomcat 심볼릭 링크 추가
sudo ln -s /usr/local/<압축해제한 폴더명> /Library/Tomcat  

# Tomcat 설치 디렉토리 및 파일 소유자 변경 
sudo chown -R <맥북 user id> /Library/Tomcat  

# Tomcat 실행/종료 스크립트의 실행 권한 추가
sudo chmod +x /Library/Tomcat/bin/*.sh 
```
