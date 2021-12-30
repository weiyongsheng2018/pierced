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
 
 TCP穿透：
 ./ding -config=./ding.cfg -proto=tcp start ssh
 
 
 参考文章1：https://blog.csdn.net/lxyoucan/article/details/112548798
 参考文章2：https://github.com/mzlogin/ding-tunnel
 参考文章3：https://gitcode.net/mirrors/mzlogin/ding-tunnel?utm_source=csdn_github_accelerator
 
 
 frp使用配置：
 福利网站：https://frp.104300.xyz/
 免费FRP
服务器：frp.104300.xyz
连接端口：7000
密码：www.126126.xyz
开放端口：80 / 443 , 10001 - 50000
免费域名：*.frp.104300.xyz
注：每周一凌晨3点服务器会自动重启，可能会造成短时服务不可用

三级域名*.frp.104300.xyz的80端口目前被封，临时解决方案：
使用8080端口（原80端口依旧可以通过科学上网方法使用，不受影响）
例如原来的网址是http://test.frp.104300.xyz，
现在换成http://test.frp.104300.xyz:8080即可访问，frp客户端设置不需要任何改变，Enjoy！
 
 [common]
server_addr = frp.104300.xyz
server_port = 7000 
token = www.126126.xyz 

[remote_desk] 
type = tcp 
local_ip = 127.0.0.1
local_port = 3389
remote_port = 47921

[web_epsoft] 
type = http
local_port = 8080
custom_domains = sonar
