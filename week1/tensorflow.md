# ubuntu下tensorflow的a安装&运行官方教程

## 安装tensorflow

tensorflow有以下几种安装方式

+ Python 和 Virtualenv：在 Python 虚拟环境中使用 TensorFlow 所需的所有包。TensorFlow 环境与同一台机器上的其他 Python 程序隔离开来。

+ Native pip：系统全局中安装 TensorFlow。可能会干扰其他 Python 安装或库。

+ Docker：Docker 是一个容器运行时环境，它将内容完全隔离在系统上预先存在的包中。在这个方法中，使用包含 TensorFlow 及其所有依赖项的 Docker 容器。这种方法非常适合将 TensorFlow 合并到已经使用 Docker 的更大的应用程序体系结构中。

这里使用创建一个虚拟环境并安装TensorFlow这种方法

创建一个名为`tf-demo`的项目目录：

>`mkdir ~/tf-demo`

导航到新创建的`tf-demo`目录：

>`cd ~/tf-demo`

创建一个名为`tensorflow-dev`的新虚拟环境。运行以下命令以创建环境：

>`python3 -m venv tensorflow`

激活后，可以在终端中看到与此类似的内容：

>`(tensorflow)username@hostname:~/tf-demo $`

现在可以在虚拟环境中安装 TensorFlow。

运行以下命令安装和升级到 PyPi 中最新版本的 TensorFlow：

>`(tensorflow-dev) $ pip3 install --upgrade tensorflow`

但是下载速度非常慢，使用清华镜像[下载tensorflow](https://pypi.tuna.tsinghua.edu.cn/simple/tensorflow/)到本地安装

也可以使用命令进行下载tensorflow-1.14版本，py版本为3.5.2：

>`wget https://pypi.tuna.tsinghua.edu.cn/packages/d3/29/cd1f608f260addce161745be44e5696c3d4ef04a9974940bce32787b2711/tensorflow-1.14.0rc1-cp35-cp35m-manylinux1_x86_64.whl`

`ls`查看已经下载好的.whl文件

![ls](https://github.com/erguixieshen/XLA/raw/master/week1/picture/4.png)

使用以下命令安装本地包(注意加引号)：

>`pip install "tensorflow-1.14.0rc1-cp35-cp35m-manylinux1_x86_64.whl"`

查看报错信息

![ls](https://github.com/erguixieshen/XLA/raw/master/week1/picture/5.png)

`tensorboard-1.14.0-py3-none-any.whl`无法下载

同样，使用其他源使用清华镜像[下载tensorboard](https://macports.mirror.ac.za/distfiles/py-tensorboard/)

