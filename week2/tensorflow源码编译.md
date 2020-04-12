# tensorflow源码编译

## 准备工作

### 安装 TensorFlow pip 软件包依赖项

>`pip install -U --user pip six numpy wheel setuptools mock 'future>=0.17.1'`</br>
    `pip install -U --user keras_applications --no-deps`</br>
    `pip install -U --user keras_preprocessing --no-deps`

### 安装 Bazel

步骤1：将Bazel发行版URI添加为包源

>`sudo apt install curl`</br>
`curl https://bazel.build/bazel-release.pub.gpg | sudo apt-key add -
echo "deb [arch=amd64] https://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list`

步骤2：安装和更新Bazel

>`sudo apt update && sudo apt install bazel`

安装后，可以在常规系统更新中升级到Bazel的较新版本：

>`sudo apt update && sudo apt full-upgrade`

该bazel软件包将始终安装Bazel的最新稳定版本。除了最新版本的Bazel之外，还可以安装特定版本的Bazel：

>`sudo apt install bazel-1.0.0`

步骤3：安装JDK

>`# Ubuntu 16.04 (LTS) uses OpenJDK 8 by default:`</br>
`sudo apt install openjdk-8-jdk`
</br>
`# Ubuntu 18.04 (LTS) uses OpenJDK 11 by default:`</br>
`sudo apt install openjdk-11-jdk`

### 使用二进制安装程序

可以从Bazel的[GitHub版本页面](https://github.com/bazelbuild/bazel/releases)下载二进制安装程序。
#
步骤1：安装所需的软件包
Bazel需要一个C ++编译器并解压缩才能工作：

>`sudo apt install g++ unzip zip`

步骤2：运行安装程序

>`./bazel-<version>-installer-linux-x86_64.sh --user`

## 下载 TensorFlow 源代码

>`  git clone https://github.com/tensorflow/tensorflow.git`
</br>
` cd tensorflow`


也可以直接下载（推荐）

>`wget https://github.com/tensorflow/tensorflow/archive/r1.14.zip`

解压

>`unzip r1.14.zip`

配置 build:通过运行 TensorFlow 源代码树根目录下的 ./configure 配置系统 build。此脚本会提示指定 TensorFlow 依赖项的位置，并要求指定其他构建配置选项（例如，编译器标记）。

>`./configure`

打开xla编译开关

![xla](https://github.com/erguixieshen/XLA/raw/master/week2/picture/1.png)



### 安装软件包

>`pip install /tmp/tensorflow_pkg/tensorflow-1.14-cp35-cp35m-linux_x86_64.whl`

## TensorFlow 生成 TensorFlow 图表

XLA（加速线性代数）是用于优化TensorFlow计算的线性代数的域特定编译器。

XLA 利用 JIT 编译技术分析用户在运行时创建的 TensorFlow 图表，根据实际运行时维度和类型将其专门化，将多个运算融合在一起并为它们生成高效的本机代码——适用于 CPU、GPU 之类的设备和自定义加速器（例如，Google 的 TPU）。





