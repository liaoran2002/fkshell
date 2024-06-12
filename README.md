# fkshell
# 使用前注意：
### 设置环境变量
```shell
vi /etc/profile.d/fk.sh
```
输入
```shell
export FK=FreeKill文件夹的位置
export FKS=fkshell文件夹的位置
export FKL=fklog文件夹的位置
export PATH=$PATH:$FK:$FKS:$FKL
```
# 每个脚本的作用
### opfk
检测服务器是否运行，不运行自动启动
### sufk
更新服务器内扩展，可以加扩展名更新指定扩展
```shell
sufk 2hu
```
### ggfk
发送狗卡公告 
```shell
ggfk 玩家名称 盒子名称 物品名称
```
效果：
玩家 **玩家名称** 在 **<font color=lightgreen>盒子名称</font>** 中获得了 **<font color=lightblue>物品名称</font>**
### msgfk
发送服务器消息，次数与间隔时间可以为空
```shell
msgfk 消息 次数 间隔时间
```
### arfk
可以定时任务，定时查询服务器状态，并自动启动服务器
```shell
crontab -e
```
输入
```shell
* * * * * arfk
```
