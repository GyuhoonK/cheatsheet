script

```bash
#!/bin/sh

# 현재 경로
SHELL_PATH=`pwd -P`
echo $SHELL_PATH 

# shell script 경로
REALATIVE_PATH=`dirname $0`
# echo $REALATIVE_PATH
cd $REALATIVE_PATH
SCRIPT_PATH=`pwd -P` #스크립트 경로
echo $SCRIPT_PATH

# DIR 경로
PROJECT_DIR="$(cd "$(dirname "${BASH_SOURCE[0]}")" && pwd)"
echo $PROJECT_DIR
```