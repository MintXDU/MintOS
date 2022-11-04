polybar上面的应用图标原来是由一个叫 tray 的东西显示的。

如果想要改变窗口的 dpi: 
  1.  修改 ~/.Xresources 文件中的 Xft.dpi
      eg: Xft.dpi: 120
  2.  执行命令: xrdb ~/.Xresources
> Polybar:
'''
sudo pacman -S polybar
'''
