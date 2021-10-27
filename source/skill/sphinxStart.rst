
2. Sphinx 基础使用
#############################

2.1 Sphinx 安装与编译
*****************************

在windows下使用需要先安装 **python** ，然后使用

::

    $ pip install -U sphinx

随后没有报错即安装成功。

Sphinx 附带一个名为 *sphinx-quickstart* 的脚本，这个脚本会设置一个源目录并创建一个默认的 conf.py 配置文件，
在创建时，它还会问你一些问题，并从中得到配置值填入配置文件中。

::

    $ sphinx-quickstart

之后如果进行编写之后需要生成 *html* 预览，使用命令

::

    $ sphinx-build -b html source build

随后生成在build中的index.html就是网页预览入口页面。

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

conf.py是配置项目使用的配置文件，里面配置项目使用的包，
例如在里面配置了html的主题sphinx_rtd_theme，需要使用pip命令安装这个包，
具体可以查阅源文件。

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