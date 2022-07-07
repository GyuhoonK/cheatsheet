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

rsync(**R**emote **SYNC**)


setcap/getcap (capabilities)
