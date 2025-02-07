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
export FKP=FreeKill进程名
export FKPRT=FreeKill端口
export PATH=$PATH:$FK:$FKS:$FKL
```

# 每个脚本的作用
### opfk
检测服务器是否运行，服务器未运行就会自动启动服务器并自动备份服务器error_log到FKL位置
```shell
opfk
```
### sufk
更新服务器内扩展，可以加扩展名更新指定扩展
例：
更新所有扩展
```shell
sufk
```
更新扩展2hu
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
FK=FreeKill文件夹的位置
FKS=fkshell文件夹的位置
FKL=fklog文件夹的位置
FKP=FreeKill进程名
FKPRT=FreeKill端口
PATH=/usr/local/bin:/usr/bin:/bin:/usr/local/games:/usr/games:$FK:$FKS:$FKL
* * * * * arfk
```
### lpfk
显示服务器内扩展情况，需安装sqlite3

sqlite3安装流程
```shell
curl https://www.sqlite.org/2024/sqlite-autoconf-3460000.tar.gz --optput sqlite3.tar.gz
tar -zxvf sqlite3.tar.gz -C .
cd sqlite-autoconf-3460000
./configure --prefix=想要安装的目录
make
make install
vi /etc/profile.d/sqlite3.sh
source /etc/profile.d/sqlite3.sh
sqlite3
```
sqlite3.sh里要写的内容
```shell
export SQLITE3_HOME=sqlite3安装目录
export PATH=$PATH:$SQLITE3_HOME/bin
```
安装好之后就可以
```shell
lpfk
```

### cfk

服务器内存占用大于1G就重启服务器

用于定时任务，用法和arfk相同

### qfk
重启服务器，可以用于定时任务或者手动重启服务器

定时任务:

用法和arfk相同

手动重启:
```shell
qfk
```

### infk
往FK服务器中安装扩展

用法：
```shell
infk 扩展网址
```

例：
```shell
infk https://gitee.com/youmuKon-supreme/2hu
```

### scfk
查询信息

用法如下:scfk [-d|-m|-p|-w|-h] [参数]

命令列表:

-d 每日日活

-m 每日月活

-p 玩家胜率 

-w 武将胜率

-h 显示此帮助信息

用法:

```shell
scfk -d
scfk -m
scfk -p 玩家名称
scfk -w 武将名称
scfk -p 玩家名称 模式名称
scfk -w 武将名称 模式名称
```

### lsfk
用法如下: lsfk [-p|-r|-h]

-p: 显示在线玩家

-r: 显示在线房间

-h: 显示此帮助信息

使用前注意:

向~/.screenrc中添加以下内容:

```shell
logfile flush 1
```
用法:

```shell
lsfk -p
lsfk -r
lsfk -h
```

```
如有脚本需求，可以发lssues
如有更好脚本，可以提交pr
```
