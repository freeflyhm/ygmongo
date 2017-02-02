docker run -d -v /"$PWD"/db:/db --name ygmongo mongo:latest

# 压缩
tar -zcvf 17xxxx.tar.gz /db/17xxxx

# 解压
tar -zxvf 17xxxx.tar.gz

# 备份数据库
mongodump -d hz -o /db/17xxxx

# 还原数据库
mongorestore -d hz /db/170202/hz
mongorestore -d gz /db/170202/gz
mongorestore -d sz /db/170202/sz
mongorestore -d auth /db/170202/auth
