paruqet-tools 
```bash
# stat
$ hadoop jar parquet-tools-1.9.0.jar dump -d -n <file path> 
# meta 
$ hadoop jar parquet-tools-1.9.0.jar meta <file path>
# 특정 컬럼(a) 만 확인
$ hadoop jar parquet-tools-1.9.0.jar -c a -d -n <file path>
```

dropTable command
```sh
# dropTable.sh 
# !/bin/sh
# sh dropTable.sh <db_name> <tbl_name>
if [ $# -ne 2 ]; then
    echo "$# is illegal number of parameters"
    echo "Usage : $0 <db_name> <tbl_name>"
    exit 1
fi
db_name=$1
tbl_name=$2
 
hive -e "DROP TABLE IF EXISTS $db_name.$tbl_name"
hdfs dfs -rm -r /user/hive/warehouse/$db_name.db/$tbl_name
```
```
# test1 테이블 이름에 pdlog가 들어간 테이블 모두 삭제
$ hive -e "show tables from test1" | grep pdlog | awk '{print "test1 " $2'} | xargs -n 2 sh dropTable.sh
```

Yarn App 종료
```bash
$ yarn app -list | awk "$2 == "pyspark-shell" {print "yarn app -kill " $1} | sh
```
