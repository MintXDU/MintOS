### 1. 通过命令行进行网络连接管理:
下载包 networkmanager
```
nmcli --help
```
### 2. 修改 vim 配置
修改文件 /etc/vimrc

### 3. 加工图片工具: ```imagemagick```
单单修改图片的后缀名称有时候是不能实质性地更改图片的属性的。\
可以使用命令
```
convert name.jpg name.png
```
把 jpg 图片转换成 png 图片。\
更多命令请通过 man 查阅。

### 4. 安装配置文件管理工具 ```chezmoi```
```
sudo pacman -S chezmoi
```
具体操作，查看[官方文档](https://www.chezmoi.io/quick-start/)。
