# E5自动续期

# 分流页面 ( 请跳转 )

AutoApi系列：~~AutoApi(v1.0)~~、~~AutoApiSecret(v2.0)~~、~~AutoApiSR(v3.0)~~、~~AutoApiS(v4.0)~~、~~AutoApiP(v5.0)~~、AutoApi(v6.0)

新版本系统 (2021-2-9采用)：

* 以后更新都在AutoApi，采用v0.0版本号进行覆盖式更新
     * [AutoApi](https://github.com/wangziyingwen/AutoApi) ： 最新版
     
* 保留1到2个稳定的简易版，防止萌新大范围报错
     * [AutoApi'X'](https://github.com/wangziyingwen/AutoApiP) ： 稳定版1

-------------------------------------------------------------------------------------------------------------------------------------------
-------------------------------------------------------------------------------------------------------------------------------------------

2021.02.26
https://blog.csdn.net/u010025179/article/details/106901560/

脚本

1.然后我们终于可以下载脚本了，点击下载，先下载到本地，然后用文本编辑器打开py脚本
2.在脚本23行和24行内分别填入之前保存的应用id和应用秘钥，保存

3.保存好脚本后再在脚本同目录下创建一个空的txt文件，重命名为1.txt,将获取的OAQ开头的那一大段token复制进1.txt，保存退出

1.py和1.txt都保存好就可以上传到服务器了,一定要保证1.py和1.txt两个文件在同目录


服务器部署(CentOS)
1.复制1.py和1.txt到同一目录下

2.执行pip3 install requests安装requests

3.执行yum install screen -y来安装screen

4.执行screen -S api这时候会进入一个新窗口,再通过cd命令进入脚本所在目录

5.执行python3 1.py就正式开始刷脚本api了，如果成功，屏幕会输出成功调用信息

6.下次登录ssh执行screen -r api就可以再看到调用信息了
7.Python3安装

    1.安装依赖环境
yum -y installgcc zlib-devel bzip2-devel openssl-devel ncurses-devel sqlite-devel readline-devel tk-devel gdbm-devel db4-devel libpcap-devel xz-devel git

    2.安装pyenv包
curl -L https://github.com/pyenv/pyenv-installer/raw/master/bin/pyenv-installer | bash

    3.将pyenv安装到系统环境变量中
echo 'export PATH="/home/python/.pyenv/bin:$PATH"' >> ~/.bash_profile
echo 'eval "$(pyenv init -)"' >> ~/.bash_profile
echo 'eval "$(pyenv virtualenv-init -)"' >> ~/.bash_profile
source ~/.bash_profile

    4.安装
pyenv install 3.8.2  //pyenv install --list 查看可以安装的python版本
我这里等了很久，不要以为死机了，等就行了
Downloading Python-3.8.2.tar.xz...
-> https://www.python.org/ftp/python/3.8.2/Python-3.8.2.tar.xz

    5.配置系统使用的Python版本

pyenv管理python版本的三个基础命令
pyenv global 配置当前用户的系统使用的python版本
pyenv shelll 配置当前shell的python版本，退出shell则失效
pyenv local 配置所在项目（目录）的python版本
为了避免乱七八糟的问题我用了local命令
cd /home/dingyue
pyenv local 3.8.2

hon版本，退出shell则失效**
- pyenv local 配置所在项目（目录）的python版本
