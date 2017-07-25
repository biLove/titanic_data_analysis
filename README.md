# 项目概述

在本项目中，将会分析 泰坦尼克号数据集，将会使用 Python 库 NumPy、Pandas 和 Matplotlib 。

# 需要安装的软件和库

需要按照 Python，和以下库

1. pandas
2. numpy
3. matplotlib
4. csv

建议安装 Anaconda，它自带所有必要的包和 IPython 笔记本。

## 安装 Anaconda

Anaconda 可用于 Windows、Mac OS X 和 Linux。可以在 https://www.continuum.io/downloads  上找到安装程序和安装说明。

如果计算机上已经安装了 Python，这不会有任何影响。实际上，脚本和程序使用的默认 Python 是 Anaconda 附带的 Python。   
选择 Python 3.6 版本（你可以在以后安装 Python 2 版本。不过，如果你是机器学习、数据分析纳米学位的学员，请选择 Python 2 版本）。此外，如果是 64 位操作系统，则选择 64 位安装程序，否则选择 32 位安装程序。继续并选择合适的版本，然后安装它。之后，继续进行！   
完成安装后，会自动进入默认的 conda 环境，而且所有包均已安装完毕，如下面所示。可以在终端或命令提示符中键入 conda list，以查看你安装的内容。

为了避免报错，我推荐在默认环境下更新所有的包。打开 Anaconda Prompt （或者 Mac 下的终端），键入：

```
conda upgrade --all
```

并在提示是否更新的时候输入 y（Yes）以便让更新继续。初次安装下的软件包版本一般都比较老旧，因此提前更新可以避免未来不必要的问题。   

### 管理包

安装了 Anaconda 之后，管理包是相当简单的。要安装包，请在终端中键入 ```conda install package_name。``` 

例如，要安装 numpy，请键入 
```conda install numpy``` 。

同时安装多个包
```conda install numpy scipy pandas``` 

通过添加版本号来指定所需的包版本。
```conda install numpy=1.10```

Conda 还会自动为你安装依赖项。例如，scipy 依赖于 numpy，因为它使用并需要 numpy。如果你只安装 scipy (```conda install scipy```)，则 conda 还会安装 numpy（如果尚未安装的话）。
大多数命令都是很直观的。

要卸载包
```conda remove package_name```

要更新包
```conda update package_name```

如果想更新环境中的所有包（这样做常常很有用）
```conda update --all```

要列出已安装的包
```conda list```

如果不知道要找的包的确切名称，可以使用 
```conda search search_term``` 进行搜索。

例如，我知道我想安装 Beautiful Soup，但我不清楚确切的包名称。因此，我尝试执行 
```conda search beautifulsoup```

### 管理环境

要创建环境，请在终端中使用 
```conda create -n env_name list of packages```

在这里，```-n env_name``` 设置环境的名称（-n 是指名称），
而 ```list of packages``` 是要安装在环境中的包的列表。

例如，要创建名为 my_env 的环境并在其中安装 numpy，请键入 
```conda create -n my_env numpy```。

创建环境时，可以指定要安装在环境中的 Python 版本。这在你同时使用 Python 2.x 和 Python 3.x 中的代码时很有用。要创建具有特定 Python 版本的环境，请键入类似于 
```conda create -n py3 python=3```
```conda create -n py2 python=2``` 

### 进入环境

创建了环境后，在 OSX/Linux 上使用 ```source activate my_env``` 进入环境。在 Windows 上，请使用 ```activate my_env```.

### 保持和加载环境

共享环境这项功能确实很有用，它能让其他人安装你的代码中使用的所有包，并确保这些包的版本正确。你可以使用 ```conda env export > environment.yaml``` 将包保存为 YAML。命令的第一部分 ```conda env export``` 用于输出环境中的所有包的名称（包括 Python 版本）。

### 列出环境

使用 ```conda env list``` 列出你创建的所有环境

### 删除环境

使用 ```conda env remove -n env_name``` 删除指定的环境

## 安装 Jupyter notebook

目前，安装 Jupyter 的最简单方法是使用 Anaconda。该发行版附带了 Jupyter notebook。你能够在默认环境下使用 notebook。 

要在 conda 环境中安装 Jupyter notebook，请使用 
```conda install jupyter notebook```

也可以通过 pip 安装
```pip install jupyter notebook```

### 启动 notebook 服务器

要启动 notebook 服务器，请在终端或控制台中输入 jupyter notebook。服务器会在你运行此命令的目录中启动。这意味着任何 notebook 文件都会保存在该目录下。你通常希望在 notebook 文件所在的目录中启动服务器，不过你也可以在文件系统中导航到 notebook 文件所在的位置。   
运行此命令时（请自己试一下！），服务器主页会在浏览器中打开。默认情况下，notebook 服务器的运行地址是 http://localhost:8888  。该地址的含义是：localhost 表示你的计算机，而 8888 是服务器的通信端口。只要 notebook 服务器仍在运行，你随时都能通过在浏览器中输入 http://localhost:8888    返回到 web 页面中。   

如果同时启动了另一个 notebook 服务器，新服务器会尝试使用端口 8888，但由于此端口已被占用，因此新服务器会在端口 8889 上运行。之后，你可以通过 http://localhost:8889   连接到新服务器。每个额外的 notebook 服务器都会像这样增大端口号。

#项目详情

## 选择数据集

泰坦尼克号数据：
包括泰坦尼克号上 2224 名乘客和船员中 891 名的人口学数据和乘客基本信息。你可以在 Kaggle 网站上查看这个数据集的详细描述。这个数据集就是来自 Kaggle。

## 分析数据

讨论有哪些因素会让船上的人生还率更高。

