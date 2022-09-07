`.DS_Store` 일괄 삭제하기
```bash
$ find . -name '.DS_Store' -type f -delete
$ git config --global core.excludesFile ~/.gitignore # global gitignore
```

ssh-key

```bash
$ ssh-keygen -m PEM -t rsa -b 4096 
# -m : format PEM (Privacy Enhanced Mail)로 생성 => Base64로 인코딩한 텍스트 형식의 파일
# -t rsa : 암호화 방식 RSA 기반 키 생성(RSA vs. DSA)
# -b 4096 : 4096 bit로 생성(default 2048 bit)
```
