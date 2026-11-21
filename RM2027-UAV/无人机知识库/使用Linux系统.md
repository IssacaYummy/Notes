# 刷写系统

刷写系统教程参考用户手册

# 切换中文桌面及中文输入法
## 切换中文桌面
输入命令
```bash
gnome-language-selector
```
可以图形化切换中文

如果提示命令不存在，使用下面的命令安装
```bash
sudo apt install language-selector-gnome
```

## 切换中文输入法
中文输入法推荐使用fcitx5：
```bash
sudo apt install fcitx5 fcitx5-chinese-addons fcitx5-config-qt \
  fcitx5-frontend-gtk3 fcitx5-frontend-qt5

im-config -n fcitx5

cat >> ~/.xprofile <<'EOF'
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
EOF

fcitx5-configtool
```

在输入法中添加拼音

# 常用工具和命令
## 查看系统占用和系统版本

查看系统占用建议使用htop
```bash
sudo apt update
sudo apt install htop
htop
```
系统版本和状态
```bash
lsb_release -a   # 系统
uname -r
df -h ~   # 硬盘
free -h   # 内存
uptime    # CPU占用
```


# 微型自主无人机系统架构
![[PixPin_2026-10-23_22-50-16.png]]

