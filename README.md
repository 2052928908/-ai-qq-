# -ai-qq-
本教程适用于在windows环境（win10/11）  
保姆级教程，保证电脑小白也能成功运行  
所有需要的依赖github仓库：[ollama](https://github.com/ollama/ollama?tab=readme-ov-file) [python](https://www.python.org/) [astrbot](https://github.com/AstrBotDevs/AstrBot) [napcat](https://github.com/NapNeko/NapCatQQ)   
# 安装所需软件:
## 部署python环境（已有的可以跳过）：
下载 [python 3.11](https://www.python.org/ftp/python/3.11.0/python-3.11.0-amd64.exe) 安装程序<code>至少需要python及3.11以上的版本</code><br>
如不能下载推荐使用镜像下载源，如 [阿里云](https://mirrors.aliyun.com/python-release/windows/?spm=a2c6h.25603864.0.0.9bbb2cfeNczwTf) 的python镜像  
下载到.exe后缀的python安装包，双击启动会进入安装程序，可以一路点击continue进行下一步  
### 验证python是否能调用：  
1. 按住win+r,打开运行框，输入cmd,点击回车  
2. 在cmd命令行内输入python，可能出现两种情况:  
(1):若无报错则说明部署成功，会返回版本号，更新时间等信息并进入python模式  
(2):若提示<code>'python' 不是内部或外部命令，也不是可运行的程序或批处理文件</code>类内容可在设置里调试环境变量，将python.exe程序添加进环境变量中:  
&emsp;&emsp;[1]:打开设置  
&emsp;&emsp;[2]:&nbsp;搜索环境变量  
&emsp;&emsp;[3]:&nbsp;点击编辑系统环境变量  
&emsp;&emsp;[4]:&nbsp;点击编辑  
&emsp;&emsp;[5]:&nbsp;新建一个环境变量，将python.exe的路径输入进去  
&emsp;&emsp;(python.exe默认地址是<code>C:\Users\Administrator\AppData\Local\Programs\Python\Python<版本号>\python.exe</code>)  
&emsp;&emsp;[6]:&nbsp;点击确定 
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
# 启用qq回复
## 让astrbot接入ollama
在astrbot后台中,在模型提供商中选择新增-ollama  
在右侧已配置的模型中选择获取模型列表,添加你自己下的模型,并启用  
接下来可以直接在astrbot里直接与模型聊天,点击右上角的chat,试着说句话可以测试是否调用ollama  
## 让napcat接入astrbot
1. 在astrbot里选择机器人-创建机器人 消息类别设置为onebot v11并启用它
2. 在napcat里反向监听astrbot,在网络设置里新建一个websoket客户端,在URL里输入
```markdown
ws://localhost:6199//ws
```
```默认使用6199端口,如果被占用也可自行更改,须保持端口号一致```  
**这样就完成了ollama对接qq的全部基础工作,可以试着给这个qq发送信息测试是否正常使用**
## 配置文件
astrbot支持手动导入配置文件,可以直接运行,本教程指讲部分自带的功能,分两个板块
### 普通配置
左侧配置文件中有一个普通配置,里面有各种功能,分4个大类,只介绍可能理解会有差异但重要的功能且普通用户可使用的功能
#### AI配置
1. Agent执行方式 : ai对话的执行器,包括Dify,Coze等执行器,本期以本地为主
2. 模型 : 在模型提供商中会启用多种模型,在这里可以设置具体的回复模型,可选择在各种情况下如默认模型调用失败或默认模型为纯文本时被输入图片等情况下用其他何种模型进行替代
3. 人格 : ai回复的人格设定,可在人格设定里添加人格(在这里进行人格的塑造)
4. 流式输出 : 可以将ai对话实时生成的部分显示出来,可以在astrbot的网页中对话中更加顺畅,目前astrbot并不支持qq的流式回复(napcat实质上是把ai输出伪装成用户输出,而qq不支持预览其他用户输入框中的内容)
5. 健康模式 : 避免敏感词汇,让ai输出更有益的内容
#### 平台配置
1. 管理员 ID : 可设置管理员id,默认为astrbot
2. 隔离会话 : 可专注与发送人的对话,不在参考群中其他人的上下文对话
3. 唤醒词 : 可设置独特唤醒词,可唤醒ai进行对话,默认私聊不需要唤醒词,@ai时会自动唤醒
#### 插件配置
可引用各种第三方插件满足更加个性化的需求
#### 拓展功能
分段回复 : 可以将ai对话切分成多段,让ai对话不那么生硬
群聊上下文感知(或聊天记忆增强) : 让ai印象更加深刻,减少记忆丢失情况
自动理解图片 : 如果模型支持图片输入(vl模型)则自动解析图片
主动回复 : 主动回复群聊的内容,可设置回复的概率
### 系统配置
文本转图像策略:remote使用远程HTML渲染,local使用PIL本地渲染,默认使用remote
文件日志 : 自动将日志写入特定路径文件夹中
Trace日志 : 独立记录Trace事件
# 进阶玩法
## 人格设定
可创建人格id及提示词,随心所欲将自己喜欢的设定喂给ai,注意不要添加相悖的设定,会让ai回复很撕裂
## 知识库
可添加ai依赖的知识库,ai需要的文献参考都在这里(在线搜索本质上也是将网络的文献作为知识库喂给ai)
## 扩展
1. 插件&插件市场 : 可以添加各种插件完成更加个性化的需求,添加所有你想要的功能
2. MCP : 赋予ai一定的权限,让它能做到一些事情如发一封邮件,运行代码等,让ai不再局限于聊天框,而是有改变现实的能力
3. skills : 更专业的执行策略,让ai更专业的执行某种任务,使其更加高效,高质量的完成任务要求
4. 管理行为 : 可对ai下达指令以完成特殊的任务
## 更多
1. 对话数据 : 可监视使用情况,观察有哪些任务通过什么方式输出对话
2. 自定义规则 : 如添加安全词等特殊内容
3. 未来任务管理 : 当你认定的时间到达,astrbot会自动唤醒并完成你布置的任务
4. SubAgent 编排 : 让ai分工合作,各取所长以达成更好的效果
5. 数据统计 : 让数据可视化,更方便观察其运行状态
6. 平台日志 : 查看后台都在做什么,更精确的观察哪里出现问题,针对性地解决问题
# 👥联系我
如果我的教程中出现错误或者有侵权部分可以添加我的qq:2052928908
如果本教程对你有帮助的话请给我一个star,真的很感谢
