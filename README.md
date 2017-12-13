# python

python virtualenv pip 


---
# Python虚拟环境（pyvenv、virtualenv)

**我们为什么需要使用虚拟环境？**

Python的包（或模块）的下载保存非常独特；有时候可能会带来问题。

不同系统，Python模块的安装位置也不一样。例如，大多数系统模块安装在 sys.prefix 环境变量指定的目录中，以Mac OS X为例：



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
