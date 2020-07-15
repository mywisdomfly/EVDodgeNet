# 学习日记

## 环境配置
### 2020年7月15日总结
这个过程真的一言难尽，太难了，竟然花了我两天时间搭建环境。

首先是构建dockerfile 来实现构建docker镜像。
**注意ros下rviz需要opengl支持才能运行，因此远程桌面一定要含有opengl不然用不了。**
几个不错的ros以及nvidia的docker
[docker-ubuntu-vnc-desktop](https://github.com/ct2034/docker-ubuntu-vnc-desktop)

[docker-ubuntu-vnc-desktop](https://github.com/fcwu/docker-ubuntu-vnc-desktop)

[docker-ubuntu-xfce-vnc-desktop](https://github.com/PaoPaoRobot/docker-ubuntu-xfce-vnc-desktop)

[cudagl](https://hub.docker.com/r/nvidia/cudagl)

### docker构建
ROS+nvidia+gui+vnc+cuda+opengl 

这个是我最后用的，这个作者写的生成脚本很好，我就一路next 但是requirements文件版本号有问题，build会出错，后面有时间修补一下。我修改了sh文件，加了服务器的一些配置

[https://github.com/trn84/recipe-wizard](https://github.com/trn84/recipe-wizard)

### 数据集下载（google云盘）
这个也是一波三折，首先需要在服务器上安装electron-ssr,最后是deb的版本能用，appimage的不能用，记得按照报错安装依赖即可。

**firefox配置代理**
然后是下载数据集，同样很麻烦。
google driver 下载大文件夹时候容易莫名其妙失败，直接下载也行，他会拆分为很多个小的压缩包，然后依次解压即可，但是要是没下全就很痛苦。还有的时候大文件不压缩，导致最后路径不太对。

解决方法是使用 [gdrive](https://github.com/gdrive-org/gdrive) （这个已经Google被封了）,需要自己申请开发者账号来使用。
这个为了突破Google封锁，一键安装编译脚本[https://github.com/mbrother2/backuptogoogle](https://github.com/mbrother2/backuptogoogle)

申请账号时候，选择桌面应用即可。

下载命令 
```bash
/root/bin/gdrive download 16dOYUxBdJNp8i3IefL3BWzAzkJQOKDN_ -r --skip
# -r表示文件夹递归下载 --skip表示跳过已知文件  代码表示文件夹ID(url最后)
```