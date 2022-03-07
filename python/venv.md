python venv / virtualenv

```bash
# 가상 환경 생성(venv)
gyuhoonkim@GyuhooncBookAir ~ % python3 -m venv test1 # 현재 사용 중인 python 버전으로 생성
# 가상 환경 생성(virtualenv)
gyuhoonkim@GyuhooncBookAir ~ % virtualenv test1 -p python3.8 # python3.8버전으로 생성
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