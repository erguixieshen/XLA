# ubuntu下tensorflow的使用&运行官方教程

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

