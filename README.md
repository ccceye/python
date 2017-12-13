# python

python virtualenv pip 


---
<font color=red># Python虚拟环境（pyvenv、virtualenv)</font>

### 我们为什么需要使用虚拟环境？

Python的包（或模块）的下载保存非常独特；有时候可能会带来问题。

不同系统，Python模块的安装位置也不一样。例如，大多数系统模块安装在 sys.prefix 环境变量指定的目录中，以Mac OS X为例：

![python-pyvenv-1.png](./python-pyvenv-1.png)

使用pip或easy_install安装的第三方模块通常安装在 site packages 目录：

![python-pyvenv-2.png](./python-pyvenv-2.png)

### 下面举一个实际的例子来说明使用虚拟环境的好处

假设你有两个Python项目－A和B，这两个项目都需要使用同一个第三方模块－tensorflow。如果这两个项目使用相同的tensorflow版本，也许不会有什么问题。

但是，当A和B项目使用不同的tensorflow版本时－A使用tensorflow 0.70版本；B使用tensorflow 0.80版本。由于Python导入模块不能区分模块版本，导致A、B不能使用tensorflow的不同版本，这在很多情况下是不能接受的。

使用虚拟环境的另一个好处是：保持开发环境的简洁、有序。

### 什么是Python虚拟环境？

Python虚拟环境可以为项目创建相互独立的开发环境，也就是你可以为每个项目安装各自使用依赖模块。

使用虚拟环境可以很好的解决上面A、B项目遇到的问题：为A、B项目分别创建虚拟环境，然后在各自的虚拟环境中安装不同的tensorflow版本。

使用虚拟环境需要借助virtualenv或pyvenv，它们的使用非常简单。

### 安装virtualenv、pyvenv

如果你使用Python 2，你可以使用pip安装virtualenv：

`$ sudo pip install virtualenv`

如果你使用Python 3，它默认安装了pyvenv。

virtualenv和pyvenv的使用方法类似。由于pyvenv是较新的工具，本文以它为例。

**创建一个存放虚拟环境的目录：**
```
$ mkdir python-env
$ cd python-env
```
**创建一个虚拟环境：**

`$ pyvenv env_A`

上面命令在当前目录创建了env_A目录，目录结构：
```
├── bin
│   ├── activate
│   ├── activate.csh
│   ├── activate.fish
│   ├── easy_install
│   ├── easy_install-3.5
│   ├── pip
│   ├── pip3
│   ├── pip3.5
│   ├── python -> python3.5
│   ├── python3 -> python3.5
│   └── python3.5 -> /opt/local/Library/Frameworks/Python.framework/Versions/3.5/bin/python3.5
├── include
├── lib
│   └── python3.5
│       └── site-packages
└── pyvenv.cfg
```
使用创建的虚拟环境env_A：

`$ source env/bin/activate`

提示符中包含env_A：

`(env_A) $`

**现在你通过pip安装的包都会安装这个虚拟环境中；导入（import）模块时也只能使用这个虚拟环境中的模块。**

如果要退出env_A虚拟环境，执行：

`(env_A) $ deactivate`

### 虚拟环境的工作原理

主要就是操作环境变量。

Python在非虚拟环境下的路径：
```
$ which python
/usr/bin/python
```
激活虚拟环境再次查看Python路径：
```
$ source env/bin/activate
(env) $ which python
/Users/snail/python-env/env_A/bin/python
```
$PATH 环境变量在激活前后不一样了：
```
$ echo $PATH
/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:
 
$ source env/bin/activate
(env) $ echo $PATH
/Users/snail/python-env/env_A/bin:/usr/local/bin:/usr/bin:/bin:/usr/sbin:/sbin:
```
你可以看看 sys.prefix 和其他Python系统环境变量。


---
# pip
https://pip.pypa.io/en/stable/installing/

### Installation
**Do I need to install pip?**

pip is already installed if you're using Python 2 >=2.7.9 or Python 3 >=3.4 binaries downloaded from python.org, but you'll need to upgrade pip.

**Additionally, pip will already be installed if you're working in a Virtual Environment created by [virtualenv](https://packaging.python.org/key_projects/#virtualenv) or [pyvenv](https://packaging.python.org/key_projects/#venv).**

>Installing with get-pip.py

To install pip, securely download [get-pip.py.](https://bootstrap.pypa.io/get-pip.py)

Then run the following:

`python get-pip.py`

>Warning

>Be cautious if you're using a Python install that's managed by your operating system or another package manager. get-pip.py does not coordinate with those tools, and may leave your system in an inconsistent state.
