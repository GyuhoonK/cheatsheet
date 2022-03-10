python venv / virtualenv

```bash
# 가상 환경 생성(venv)
gyuhoonkim@GyuhooncBookAir ~ % python3 -m venv test1 # 현재 사용 중인 python 버전으로 생성
# 가상 환경 생성(virtualenv)
gyuhoonkim@GyuhooncBookAir ~ % virtualenv test1 -p python3.8 # python3.8버전으로 생성
gyuhoonkim@GyuhooncBookAir ~ % ls
test1
```

```bash
# 가상 환경 실행
gyuhoonkim@GyuhooncBookAir ~ % source test1/bin/activate
(test1) (base) gyuhoonkim@GyuhooncBookAir % which python3
/Users/gyuhoonkim/Documents/test1/bin/python3
(test1) (base) gyuhoonkim@GyuhooncBookAir % python3 -V 
Python 3.9.5
```

```bash
# 가상환경 비활성화
(test1) (base) gyuhoonkim@GyuhooncBookAir % deativate
```

```bash
# 가상환경 내보내기(export)
(test1) (base) gyuhoonkim@GyuhooncBookAir % pip insatll venv-pack
(test1) (base) gyuhoonkim@GyuhooncBookAir % venv-pack -s test1.tar.gz
(test1) (base) gyuhoonkim@GyuhooncBookAir % deativate
gyuhoonkim@GyuhooncBookAir % ls
test1 
test1.tar.gz
```

```bash
# lib 설치 및 압축
pip freeze # 설치 라이브러리 확인
pip install -t <dir name> -r <requirements>
pip install -t dependencies -r requirements.txt
zip -r9 ../dependencies.zip 
```