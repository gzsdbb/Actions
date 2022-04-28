iStoreOS 离线包不是一个压缩包，也没啥黑科技，而是借助第三方软件实现。

原理是这个项目：https://github.com/megastep/makeself

把 ipk 跟 install.sh 结合在一起，本质会生成一个包含所有 ipk 跟 install.sh 的自解压自运行的程序


把 ipk 跟 install.sh 放同一目录 （注意先设置好所有文件的权限可运行 要不然打包好运行的时候会提示没有权限）

命令行:
./makeself.sh --nox11 ./目录 包名.run "OneClick install" ./install.sh

  install.sh文件简单内容为
  
opkg update
opkg install *.ipk

更高级的脚本可以自己研究
