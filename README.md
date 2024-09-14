# jenkins

```sh
# 拉取仓库
❯ git clone https://github.com/sstutu/jenkins.git
# cd 到目录
❯ cd jenkins
# 创建jenkins组(容器运行后容器内的用户是jenkins如下:)
# ❯ docker exec -it jenkins-blueocean bash
# jenkins@d25bae64f2c9:/$ id
# uid=1000(jenkins) gid=1000(jenkins) groups=1000(jenkins)
# jenkins@d25bae64f2c9:/$ exit
# exit

# 添加jenkins组 
❯ sudo groupadd jenkins
# 当前用户加入jenkins组
❯ sudo usermod -aG jenkins $USER
# 创建挂载文件夹(确保当前是在git拉取后的jenkins文件夹内)
❯ mkdir jenkins-data
❯ mkdir jenkins-docker-certs
# 创建挂载文件夹
sudo chown -R 1000:jenkins ./jenkins-data
sudo chown -R 1000:jenkins ./jenkins-docker-certs
# 授权文件夹r:4 w:2 x:1 文件夹属主rwx 文件属组rwx 其他:r-x
sudo chmod -R 775 ./jenkins-data
sudo chmod -R 775 ./jenkins-docker-certs
```