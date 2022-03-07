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