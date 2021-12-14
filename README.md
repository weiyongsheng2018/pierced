# pierced
钉钉内网穿透

TCP 穿透需要在数据库里面执行：
GRANT ALL PRIVILEGES ON *.* TO root@'%' IDENTIFIED BY '123456';
FLUSH PRIVILEGES;
数据库连接命令：
mysql -h vaiwan.com -u root -p -P 1234 //端口号地址

钉钉内网穿透开放平台：
https://ding-doc.dingtalk.com/doc#/kn6zg7/hb7000

windows平台使用在cmd窗口执行：
 
 ding -config=ding.cfg -subdomain=xxxxx  port

 ding -config=ding.cfg -subdomain=sonar  8000
 
 Linux平台使用在终端执行：
 
 当前：nohup ./ding -config=ding.cfg -subdomain=xxxxx  port  &

 绝对路径：nohup /root/linux/ding -config=ding.cfg -subdomain=sonar  8000 &
