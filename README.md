# -ai-qq-
本教程适用于在windows环境（win10/11）  
保姆级教程，保证电脑小白也能成功运行  
所有需要的依赖github仓库：[ollama](https://github.com/ollama/ollama?tab=readme-ov-file) [python](https://www.python.org/) [astrbot](https://github.com/AstrBotDevs/AstrBot) [napcat](https://github.com/NapNeko/NapCatQQ)   
# 部署环境
## 部署python环境（已有的可以跳过）：
下载 python 安装程序<code>需要python3.11以上的版本</code><br>
如不能下载推荐使用镜像下载源，如 [阿里云](https://mirrors.aliyun.com/python-release/windows/?spm=a2c6h.25603864.0.0.9bbb2cfeNczwTf) 的python镜像  
下载到.exe后缀的python安装包，双击启动会进入安装程序，可以一路点击continue进行下一步  
### 验证python是否能调用：  
&emsp;&emsp;1:按住win+r,打开运行框，输入cmd,点击回车  
&emsp;&emsp;2:在cmd命令行内输入python，可能出现两种情况  
&emsp;&emsp;&emsp;(1)若无报错则说明部署成功，会返回版本号，更新时间等信息并进入python模式  
&emsp;&emsp;&emsp;(2)若提示<code>'python' 不是内部或外部命令，也不是可运行的程序或批处理文件</code>类内容:   
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
下载完成后直接双击安装就好，安装完成后建议同时下载模型  
(在模型页选择一个想要的模型，随便发布一句对话就会自动下载)
## 安装astrbot
下载 [astrbot](https://github.com/Raven95676/astrbot-launcher/archive/refs/tags/v0.2.4.zip) 下载后解压:  
&emsp;&emsp;无法解压的可以下载[bandzip](https://www.bandisoft.com/bandizip/dl.php?web)，安装评价版再解压  
&emsp;&emsp;完成后进入astrbot目录，在本目录下进入powershell:  
&emsp;&emsp;<code>推荐方法:</code>在文件夹里上方有路径，直接点击就会出现一串路径，输入powershell  
&emsp;&emsp;<code>备用方法:</code>点击win+r键，输入powershell并回车，利用cd命令<code>cd [你解压的路径]</code>  
&emsp;&emsp;将路径中的<code>launcher_astrbot_en.bat</code>拖入powershell里
