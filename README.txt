* 我的archlinux 所有安装包
$ pacman -Qqe > pkglist.txt [包导出]
$ sudo pacman -S - < pkglist.txt [包导入]
$ sudo pacman -S $(comm -12 <(pacman -Slq | sort) <(sort pkglist.txt)) [移除pacman的额外包 如aur中的包]
$ sudo pacman -Rsu $(comm -23 <(pacman -Qq | sort) <(sort pkglist.txt)) [删除系统中 除备份列表的所有包]
