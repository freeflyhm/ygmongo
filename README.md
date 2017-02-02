docker run -d -v /"$PWD"/db:/db --name ygmongo mongo:latest

docker exec -it ygmongo /bin/sh

# 压缩
tar -zcvf 170202.tar.gz /db/170202

# 解压
tar -zxvf 170202.tar.gz

# 备份数据库
mongodump -d hz -o /db/170202

# 还原数据库
mongorestore --noIndexRestore -d hz /db/170202/hz
mongorestore --noIndexRestore -d gz /db/170202/gz
mongorestore --noIndexRestore -d sz /db/170202/sz
mongorestore --noIndexRestore -d auth /db/170202/auth
