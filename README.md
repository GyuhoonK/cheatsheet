# cheatsheet
작고 소중한 나의 코딩 팁



## Bash Shell

ssh(**S**ecure **SH**ell)

```bash
ssh -p <port> <remote>
ssh -p 22 gyuhoonk@server_ip 
```

scp(**S**ecure **C**o**P**y, 서버 간 파일 전송)

```bash
scp -p <port> <src> <dst>
# Local -> Server
scp data.txt gyuhoonk@server_ip:/home/gyuhoonk # 파일 전송
scp -r data gyuhoonk@server_ip:/home/gyuhoonk # 디렉토리 전송
# Server -> Local
scp gyuhoonk@server_ip:/home/gyuhoonk ~/Downloads # 파일 전송
scp -r gyuhoonk@server_ip:/home/gyuhoonk/data ~/Downloads # 디렉토리 전송
```

background

```bash
# nohup(NO Haing UP)
gyuhoonkim@GyuhooncBookAir ~ % nohup run.sh > /dev/null 2>&1 &

# bg
gyuhoonkim@GyuhooncBookAir ~ % sh run.sh 
[1] + Stopped # crtl + z
gyuhoonkim@GyuhooncBookAir ~ % bg # 현재 실행 중인 프로세스를 백그라운드로 전환
gyuhoonkim@GyuhooncBookAir ~ % jobs # 백그라운드 프로세스 확인

# screen
gyuhoonkim@GyuhooncBookAir ~ % screen -S test1 # test1 screen 생성 및 진입
gyuhoonkim@GyuhooncBookAir ~ % sh run.sh # test1 screen 에서 실행
# crtl a + d : screen 탈출(detached)
gyuhoonkim@GyuhooncBookAir ~ % screen -list
There is a screen on:
	1366.test1	(Detached)
1 Socket in /var/folders/j7/6fjlvc6j3_v12m6sr_187zc00000gn/T/.screen.
gyuhoonkim@GyuhooncBookAir ~ % screen -S test1 -X quit # screen 종료
```

process

```bash
# grep 이용
ps -ef | grep gyuhoonk # 프로세스 설명 라인에 gyuhoonk가 들어간 모든 프로세스 출력
# awk 이용
ps -ef | awk '$2==1346 {print $0}' # pid가 1346인 라인 출력
ps -ef | awk '$2>1346 {print "kill -9 $2"}'
#pyspark-shell 인 App 리스트를 모두 kill하는 shell 작성
yarn app -list | awk '$2=="pyspark-shell" {print "yarn app -kill $1 # $2"}' 1>kill-pyspark-shell.sh
```

etc

```bash
# 파일 개수 확인
ls -l | grep ^- | wc -l
```

script

```bash
#!/bin/sh
SHELL_PATH=`pwd -P`
echo $SHELL_PATH # 현재 쉘 경로

REALATIVE_PATH=`dirname $0`
# echo $REALATIVE_PATH
cd $REALATIVE_PATH
SCRIPT_PATH=`pwd -P` #스크립트 경로
echo $SCRIPT_PATH
```

python venv / virtualenv

```bash
# 가상 환경 생성(venv)
gyuhoonkim@GyuhooncBookAir ~ % python3 -m venv test1 # 현재 사용 중인 python 버전으로 생성
# 가상 환경 생성(virtualenv)
# gyuhoonkim@GyuhooncBookAir ~ % virtualenv test1 -p python3.8 # python3.8버전으로 생성
gyuhoonkim@GyuhooncBookAir ~ % ls
test1

# 가상 환경 실행
gyuhoonkim@GyuhooncBookAir ~ % source test1/bin/activate
(test1) (base) gyuhoonkim@GyuhooncBookAir % which python3
/Users/gyuhoonkim/Documents/test1/bin/python3
(test1) (base) gyuhoonkim@GyuhooncBookAir % python3 -V 
Python 3.9.5

# 가상환경 비활성화
(test1) (base) gyuhoonkim@GyuhooncBookAir % deativate
```



## Python

file path

```python
import os

#현재 파일 이름 : cwd를 기준으로 출력
print(__file__)

#현재 파일 실제 경로
print(os.path.realpath(__file__))

#현재 파일 절대 경로
print(os.path.abspath(__file__))

#현재 폴더(cwd) 경로
print(os.getcwd())

#현재 파일의 폴더 경로; 작업 파일 기준
print(os.path.dirname(os.path.realpath(__file__)))
```

args

```python
# python3 argparse_test.py --first apple --second banana
# python3 argparse_test.py -f apple -s banana
import argparse
parser = argparse.ArgumentParser()
parser.add_argument("-f", "--first", required=True)
parser.add_argument("-s", "--second", required=True)
args = parser.parse_args()
print("First arg is ", args.first) # args.f 
#apple
print("Second arg is ", sys.second) # args.s
#banana

# python3 argv_test.py apple banana
import sys
print("This is the name of the script: ", sys.argv[0])
#argv_test.py
print("First argv is ", sys.argv[1])
#apple
print("Second argv is ", sys.argv[2])
#banana
# print("Third arv is ", sys.arv[3])
# Error
```
