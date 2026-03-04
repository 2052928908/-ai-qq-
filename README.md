# -ai-qq-
本教程适用于在windows环境（win10/11）  
保姆级教程，保证电脑小白也能成功运行  
所有需要的依赖github仓库：[ollama](https://github.com/ollama/ollama?tab=readme-ov-file) [python](https://www.python.org/) [astrbot](https://github.com/AstrBotDevs/AstrBot) [napcat](https://github.com/NapNeko/NapCatQQ)   
# 安装所需软件:
## 部署python环境（已有的可以跳过）：
下载 python 安装程序<code>需要python3.11以上的版本</code><br>
如不能下载推荐使用镜像下载源，如 [阿里云](https://mirrors.aliyun.com/python-release/windows/?spm=a2c6h.25603864.0.0.9bbb2cfeNczwTf) 的python镜像  
下载到.exe后缀的python安装包，双击启动会进入安装程序，可以一路点击continue进行下一步  
### 验证python是否能调用：  
&emsp;&emsp;1.按住win+r,打开运行框，输入cmd,点击回车  
&emsp;&emsp;2.在cmd命令行内输入python，可能出现两种情况  
&emsp;&emsp;&emsp;(1):若无报错则说明部署成功，会返回版本号，更新时间等信息并进入python模式  
&emsp;&emsp;&emsp;(2):若提示<code>'python' 不是内部或外部命令，也不是可运行的程序或批处理文件</code>类内容:   
&emsp;&emsp;&emsp;&emsp;&nbsp;可在设置里调试环境变量，将python.exe程序添加进环境变量中:  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[1]&nbsp;打开设置  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[2]&nbsp;搜索环境变量  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[3]&nbsp;点击编辑系统环境变量  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[4]&nbsp;点击编辑  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[5]&nbsp;新建一个环境变量，将python.exe的路径输入进去  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;(python.exe默认地址是<code>C:\Users\Administrator\AppData\Local\Programs\Python\Python<版本号>\python.exe</code>)  
&emsp;&emsp;&emsp;&emsp;&emsp;&nbsp;[6]&nbsp;点击确定 
## 安装ollama：
下载&nbsp;[ollama](https://ollama.com/download/OllamaSetup.exe)&nbsp;并安装  
### 模型下载:
<code>推荐方法:</code>在模型页选择一个想要的模型，随便发布一句对话就会自动下载
<code>备用方法:</code>在cmd命令行输入ollama run <你要跑的模型>
## 安装并使用astrbot:
下载 [astrbot](https://github.com/Raven95676/astrbot-launcher/archive/refs/tags/v0.2.4.zip) 下载后解压:  
&emsp;&emsp;无法解压的可以下载[bandzip](https://www.bandisoft.com/bandizip/dl.php?web)，安装评价版再解压  
&emsp;&emsp;完成后进入astrbot目录，在本目录下进入powershell:  
&emsp;&emsp;<code>推荐方法:</code>在文件夹里上方有路径，直接点击就会出现一串路径，输入powershell  
&emsp;&emsp;<code>备用方法:</code>点击win+r键，输入powershell并回车，利用cd命令<code>cd [你解压的路径]</code>  
&emsp;&emsp;确定路径后将本路径文件夹中的<code>launcher_astrbot_en.bat</code>拖入powershell里.输入一个空格后输入<code>server</code>并回车
### 进入astrbot
在浏览器输入:
```markdown
localhost:6185
```
这样就进入了astrbot后台,默认密码和账号都是astrbot,第一次登陆需要重置密码,重置后就没事了  
## 安装napcat
下载[naocat](https://github.com/NapNeko/NapCatQQ/releases/download/v4.17.30/NapCat.Shell.Windows.OneKey.zip) 并解压  
解压后运行```NapCatInstaller.exe```程序,它会自动安装需要的依赖,完成后打开该目录下的```NapCat.xxxxx.Shell```&emsp;**(其中xxxxx是qq版本)**  
里面的```napcat.bat```就是启动程序,双击打开就行
### 使用napcat
在浏览器中输入:
```markdown
localhost:6099
```
即可进入napcat后台,提示需要token key 在napcat的运行框里有一段token=xxxxxxxxxxxx **(其中xxxxxxxxxxxx是token key 一般12位)**  
输入这个key就可以进入登陆页面了
每次开启需要登陆qq,扫码就可以了  
# **打通链路**
## 让astrbot接入ollama
在astrbot后台中,在模型提供商中选择新增-ollama  
在右侧已配置的模型中选择获取模型列表,添加你自己下的模型,并启用  
接下来可以直接在astrbot里直接与模型聊天,点击右上角的chat,试着说句话可以测试是否调用ollama  
## 让napcat接入astrbot
1. 在astrbot里选择机器人-创建机器人 消息类别设置为onebotv11并启用它
2. 在napcat里反向监听astrbot,在网络设置里新建一个websoket客户端,在URL里输入
```markdown
ws://localhost:6199//ws
```
   
