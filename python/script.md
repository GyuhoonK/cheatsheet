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