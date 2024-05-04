# kkViewInstallationGuide
1. 环境要求
Java: 1.8+
LibreOffice或OpenOffice(Windows下已内置，CentOS或Ubuntu下会自动下载安装，MacOS下需要自行安装)
2. 部署运行
1). 物理机或虚拟机上运行
从 码云发行版本 下载最新版发行包
解压kkFileView-x.x.x文件（Windows用.zip包，Linux/MacOS用.tar.gz包）
打开解压后文件夹的bin目录，运行startup脚本（Windows下以管理员身份运行startup.bat，Linux以root用户运行startup.sh）
浏览器访问本机8012端口 http://127.0.0.1:8012 即可看到项目演示用首页
2). Docker容器环境环境运行
拉取镜像
# 网络环境方便访问docker中央仓库
docker pull keking/kkfileview:4.1.0

# 网络环境不方便访问docker中央仓库
wget https://kkview.cn/resource/kkFileView-4.1.0-docker.tar
docker load -i kkFileView-4.1.0-docker.tar
运行
docker run -it -p 8012:8012 keking/kkfileview:4.1.0
浏览器访问容器8012端口 http://127.0.0.1:8012 即可看到项目演示用首页

3. 项目接入使用
当您的项目内需要预览文件时，只需要调用浏览器打开本项目的预览接口，并传入须要预览文件的url，示例如下：

3.x.x 及以上版本
<script type="text/javascript" src="https://cdn.jsdelivr.net/npm/js-base64@3.6.0/base64.min.js"></script>

var url = 'http://127.0.0.1:8080/file/test.txt'; //要预览文件的访问地址
window.open('http://127.0.0.1:8012/onlinePreview?url='+encodeURIComponent(Base64.encode(previewUrl)));
2.x.x 及以下版本
var url = 'http://127.0.0.1:8080/file/test.txt'; //要预览文件的访问地址
window.open('http://127.0.0.1:8012/onlinePreview?url='+encodeURIComponent(previewUrl));
详细使用说明见 使用指南
