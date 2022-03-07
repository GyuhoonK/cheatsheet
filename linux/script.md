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