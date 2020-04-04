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

![1](https://github.com/erguixieshen/XLA/raw/master/week1/picture/5.png)

`tensorboard-1.14.0-py3-none-any.whl`无法下载

同样，使用其他源使用清华镜像[下载tensorboard](https://macports.mirror.ac.za/distfiles/py-tensorboard/)

或使用以下命令下载`tensorboard-1.14.0-py3-none-any.whl `版本

>`wget https://macports.mirror.ac.za/distfiles/py-tensorboard/tensorboard-1.14.0-py3-none-any.whl`

安装

>`pip install "tensorboard-1.14.0-py3-none-any.whl"`

![1](https://github.com/erguixieshen/XLA/raw/master/week1/picture/7.png)

无法下载`grpcio-1.28.1-cp35-cp35m-manylinux2010_x86_64.whl`

同样利用上述方法将缺少与无法下载的包安装好

最后tensorflow安装成功

![1](https://github.com/erguixieshen/XLA/raw/master/week1/picture/8.png)

## 验证安装是否成功

启动 Python 解释器：

>`(tensorflow-dev) $ python`

导入 TensorFlow 包，并将其作为本地变量 tf。：

>`import tensorflow as tf`

接下来，添加这行代码来设置信息"Hello, world!"：

>`hello = tf.constant("Hello, world!")`

然后创建一个新的 TensorFlow 会话并将其分配给变量 sess：

>`sess = tf.Session()`

最后，输入这一行代码，打印出在之前的代码行中构建的 hello TensorFlow 会话的结果：

>`print(sess.run(hello))`

控制台中看到如下输出：

![1](https://github.com/erguixieshen/XLA/raw/master/week1/picture/9.png)

