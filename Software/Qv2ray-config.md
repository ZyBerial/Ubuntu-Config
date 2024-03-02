# `Qv2ray`配置

## 版本记录

1. `ubuntu`版本：`Ubuntu 22.04.4LTS`
2. `Qv2ray`版本：`Qv2ray v2.7.0-The End`

## 开始安装

### 下载软件与插件

1. `Qv2ray`仓库：`https://github.com/Qv2ray/Qv2ray/releases/download/v2.7.0/Qv2ray-v2.7.0-linux-x64.AppImage`  
2. 插件安装  
    > `https://github.com/Qv2ray/QvPlugin-Trojan/releases/tag/v3.0.0-pre3`  
    > `https://github.com/Qv2ray/QvPlugin-SSR/releases/tag/v3.0.0-pre3`  
    > `https://github.com/Qv2ray/QvPlugin-NaiveProxy/releases/tag/v3.0.0-pre3`  
    > `https://github.com/Qv2ray/QvPlugin-Trojan-Go/releases/tag/v3.0.0-pre3`  
    > `https://github.com/Qv2ray/QvPlugin-SS/releases/tag/v3.0.0-pre3`  
    > `https://github.com/Qv2ray/QvPlugin-Command/releases/tag/v3.0.0-pre3`  
3. 下载`v2ray-core`:`https://github.com/v2fly/v2ray-core/releases/download/v4.42.0/v2ray-linux-64.zip`  
当前测试通过的最高版本：`4.27.5`

## 使用

1. 运行`.AppImage`文件  

    为`.AppImage`文件添加权限

    ```shell
    sudo chmod +x Qv2ray-v2.7.0-linux-x64.AppImage
    ```

    直接运行`.AppImage`文件

    ```shell
    ./Qv2ray-v2.7.0-linux-x64.AppImage
    ```

2. 添加插件，添加`core`  
    将插件移动到对应目录 `/home/yuzheng/.config/qv2ray/plugins`

    ```shell
    mv *.so /home/yuzheng/.config/qv2ray/plugins
    ```

    解压文件，将`core`移动到对应目录

    ```shell
    unzip v2ray-linux-64.zip
    cp * ~/.config/qv2ray/plugins
    ```

3. 为`.AppImage`文件创建`.desktop`文件
    创建`.desktop`文件

    ```shell
    cd ~/桌面/
    touch 软件名.desktop
    ```

    编辑`.desktop`文件。`name, Exec, Icon`填自己的：

    ```shell
    [Desktop Entry]
    Encoding=UTF-8
    Name=软件名称
    Exec=/home/用户名/AppImage/软件名.AppImage
    Icon=/home/用户名/.icons/某某/png
    Terminal=False
    Type=Application
    StartupNotify=False
    Categories=Application;Development
    ```

    修改该文件权限为可读可写，作为可执行文件。最后拷贝到指定路径。
    ```sudo mv ~/桌面/软件名称.desktop  /usr/share/applications```
    然后就可以在收藏夹里看到它了，打开它，然后在dock栏看到它，右键它，添加到收藏夹即可。

## 安装过程的坑

1. `Ubuntu22.04`无法直接运行`.AppImage`文件。缺少`FUSE`（用户空间中的文件系统）库

> 安装`FUSE`库.  
> ```sudo apt install libfuse2```
