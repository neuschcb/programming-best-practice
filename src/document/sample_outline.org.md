# 概要设计模板：

本模板来自[Github Gist](https://gist.github.com/jouyouyun/d76e672e76397bc1d0982816f7ef773d)

# XXX概要设计

### 概述

#### 目的

本文档是针对XXX系统给出的系统概要设计文档，在本文档中，将给出XXX系统的系统设计原则、关键静态结构设计、关键动态流程设计、数据结构设计、人机交互设计、非功能性设计、系统部署与实施设计、版本维护设计等内容。

XXX系统的系统设计与实现基于XXX系统的需求分析，总体上将结合形式化设计的方法与文字描述，给出半形式化的概要设计与低层设计，与需求分析内容的相对应，以保证系统设计的严谨性与可实现性。在形式化部分，本文档将主要采取UML语言的包图、类图、序列图等进行系统设计。

本文档的适用读者为XXX系统的产品经理、设计人员、开发人员、测试人员以及后续维护人员。

#### 设计原则

在本小节应阐述本系统在设计时主要考虑到的问题。例如文件搜索主要考虑的问题是搜索速度、资源占用、架构兼容等，窗口管理器主要考虑的问题是freedesktop的协议遵循性、已知的主要违反协议软件的绕过、渲染的性能等。

还可以在这里阐述在设计时主要考虑了哪些问题，例如为什么要使用某种开源协议、为什么要使用Qt而不是gtk，为什么要使用dtk，为什么要使用kprobes而不是ftrace，为什么要使用QtWidget而不是QML，为什么要使用QCef而不是QtWebengine或者QtWebkit等。

#### 术语说明

如:

+ SSOOS：Security Subsystem Of Operating System，操作系统安全子系统

#### 参考资料

如:

+ 沈晴霓，卿斯汉 操作系统安全设计 机械工业出版社 2013年9月

### 系统设计

在这里需要给出一个大图，或者文字说明本系统中所包含的所有子系统或者模块，以及本系统与哪些外部系统需要进行交互（编译和运行时都依赖于哪些软硬件，包括具体的版本）。
这里的图需要表现的是静态结构，用自己熟悉的工具做图, 图的内容可以是:

+ 整体系统结构
+ 分层图，也就是类似多层架构设计的图

关键结构的也可以使用表格来描述, 如:

| 成员名称 | 说明 |
|----------+------|
| XXX      | XXXX |

#### 模块结构

##### 模块A

下面是每个主要模块（不需要写不重要的模块）的设计，包括模块内部的子模块结构、功能、子模块之间的接口，以及具体由哪个子模块实现父模块与外部模块之间的接口。

##### 模块B

#### 关键流程设计

关键流程指的是本系统中最关键的功能，例如对于文件搜索来说包括建立索引与文件搜索，对于窗口管理器来说是窗口的焦点、大小、位置与边框的管理。

在这里可以结合上述的静态模块结构设计与接口给出流程设计，例如模块A依赖于模块B，而且模块B提供了接口b1，
则在某个关键流程里应该就可以有A调用B的b1方法，传入某某参数，得到某某返回值的连线。
建议使用UML的序列图（如图2.5）、协作图（如图2.6）、活动图（如图2.7）、状态图（如图2.8）等来绘制，推荐使用序列图绘制，
状态图主要针对一个模块或者子模块内部的流程或者逻辑设计，其它的是多个模块之间的配合以完成功能的流程设计。

除了图以外，要在每个图下面说明

#### 关键数据结构设计

包括应用软件外部存储的主要数据结构（例如文件搜索的索引文件内容），应用程序内部主要的数据结构、使用到的数据库的主要库表设计、关键的配置数据等。最好给出哪些数据结构被哪些模块使用到了。

#### 主要人机交互设计

对于有图形界面的软件，应给出关键的人机交互设计，包括主要的界面线框图设计，以及各个界面之间的流转等。最好给出主要的图形界面与模块的对应关系。

### 非功能性设计

下面几项可以不用都写，因为不是每个软件都需要考虑到所有点。

#### 性能

例如：

+ 启动时间设计优化
+ 资源（处理器、内存、硬盘、网络）占用设计优化
+ 减少对系统或者其他软件运行的性能影响设计考量
+ 数据吞吐量或者用户响应延迟设计优化

具体例如：

+ 使用了什么算法或者数据结构
+ 使用了什么高效的库
+ 使用了无锁设计或者高性能并发程序设计
+ 使用缓存
+ 使用了异步IO，等等。

可以结合前述的具体模块与流程来体现如何在模块设计时或者整体系统设计时考虑了性能问题。

#### 安全性

例如：

+ 输入密码等认证信息是否使用了加密手段进行输入保护和数据传输
+ 加密强度是否高
+ 图形界面程序是否使用了root权限运行（含capabilities）运行