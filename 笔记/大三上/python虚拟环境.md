# Python 开发环境搭建-虚拟环境的安装和配置

## 1. virtualenv 的下载和安装

pip install virtualenv

可使用镜像加速

pip install -i https://pypi.douban.com/simple/ virtualenv

## 2. virtualenv 使用

1. 终端键入：virtualenv scrapytest，会新建文件夹scrapytest
2. 进入文件夹下的scripts文件键入：activate.bat,进入虚拟环境
3. 终端键入：python
4. 终端键入：deactivate.bat退出虚拟环境
5. 如果要切换不同的python版本，再更改第一步为：virtualenv -p E:\python\python37\python.exe(python.exe的目录) scrapytest

## 3. virtualenvwrapper 的下载和使用

pip install virtualenvwrapper-win

添加系统变量WORKON_HOME,目录在D盘下的env文件夹中

终端键入：workon,查看虚拟环境列表

键入：mkdirtualenv py3,新建虚拟环境

键入：deactivate.bat,退出

退出后，workon py3,可直接进入该虚拟环境

如果要切换不同的python版本，再更改第一步为：mkdvirtualenv --python=E:\python\python37\python.exe(python.exe的目录) scrapytest

