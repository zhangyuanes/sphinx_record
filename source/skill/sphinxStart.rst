
2. Sphinx 基础使用
#############################

2.1 Sphinx 安装与编译
*****************************


2.2 Sphinx 项目结构
*****************************

::

    在本项目中，文档的结构目录如下

    ➜  sphinx_doc git:(master) ✗ tree -L 2
    .
    ├── build
    │   ├── doctrees
    │   └── html
    ├── Makefile
    ├── README.rst
    └── source
        ├── conf.py
        ├── index.md
        ├── offer
        ├── skill
        ├── _static
        └── _templates


其中build是生产输出的代码，和编写无关。

Makefile是自动生产，一般不需要管。

README.rst或者README.md是项目的概况，如果用仓库管理也会显示在仓库的主页中。

source文件夹是项目全部源文件的文件夹：

conf.py是配置项目使用的配置文件，里面配置项目使用的包，例如在里面配置了html的主题sphinx_rtd_theme，具体可以查阅源文件。

index.md是项目的侧边目录结构，用来定位和管理侧边目录。

::

    Welcome to zhangyuanes' documentation!
    =============================================

    .. toctree::
        :maxdepth: 2
        :caption: Contents:

        offer/contents
        skill/contents

这里是暂时有两个项目结构，分别是offer和skill，下面的文件就是一篇篇文章了。

::

    ├── offer
    │   ├── backtracking.rst
    │   ├── bit.rst
    │   ├── contents.rst
    │   ├── index.rst
    ...
    │   └── tree.rst
    ├── skill
    │   ├── contents.rst
    │   ├── index.rst
    │   ├── rstStart.rst
    │   └── sphinxStart.rst


其中里面有两个文件需要注意一下，分别是 contents.rst 和 index.rst。

在这里我使用contents.rst管理项目内的侧边栏目录，使用index.rst来作为项目内说明文档。其他文章就嵌套在文件夹下，备注在contents中即可正常渲染。