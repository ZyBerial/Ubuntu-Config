# AppImage 二进制文件生成快捷方式

## `.desktop`文件

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
