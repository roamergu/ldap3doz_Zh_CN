ldap3 简介
#################
ladp3是一套严格遵从RFC 4510 LDAP V3规范的、完全使用python实现的库。ldap3 已经经过 **彻底重写** ，在 **Python 2, Python 3, PyPy, PyPy3 与Nuikta** 下均使用同样的基础代码，只要运行python的系统能够通过python解释器和python标准库访问网络，ldapv3就能正常运行。

授权
-------
ldap3库 是基于 **LGPL v3 授权** (http://www.gnu.org/licenses/lgpl-3.0.html) 发布的开源软件，这意味着你可以使用ldap3开发任意应用，无论是私有软件还是开源软件，你也可以复制、分发和修改ldap3,修改后的ldap3的描述和授权要在LGPL协议下免费。基于ldap3的衍生库必须在LGPL下授权，但使用了ldap3的应用软件则不必如此。

RFC规范性
---------------
ladp3 严格遵守最新的RFC（自2015年起）文档对于 LDAP3协议的描述：

* **最新的 LDAP V3 RFC文档** （2006） 淘汰了之前的RFC3377（2251-2256, 2829, 2830, 3371）并对LDAP 协议做了修改和整理。
* 所有的ASN1定义重新写进了RFC 4511。

为了避免不必要的服务器和网络负载造成搜索性能下降，ladp3有意地避开了RFC4511(4.5.4.1.8.1)中对于搜索选项的规定：在响应一个没有指定属性的空列表搜索请求时，应该返回所有的用户属性。相反地，在使用ldap3时你必须明确指定要请求的属性或者使用ladp3.ALL_ATTRIBUTES搜索选项。


ldap3允许在创建GroupOfNames object的时候给出一个空列表，即使LDAPV3的官方架构里不允许这么干。

ldap3允许通过 Unix sockets（ (ldapi:// scheme, LDAP over IPC) ）通信，即使并没有任何官方RFC文档要求这一点。

PEP8 规范性
---------------
除了对单行长度的规定以外，ldap3遵循PEP8规范。PEP8 (https://www.python.org/dev/peps/pep-0008/) PEP8是一个被应用在Python标准库和其他很多项目上的代码风格指南。他在“代码首先使用来被阅读，其次才是被编写”的原则下为代码的可维护性和可读性提供了一个一致的实现方式。

主页
---------
ldap3的项目主页地址： https://github.com/cannatag/ldap3


文档
-------------

可用的文档地址： http://ldap3.readthedocs.org. 你也可以在 https://media.readthedocs.org/pdf/ldap3/stable/ldap3.pdf 下载文档的PDF版本。本翻译完成之后会替换成对应的中文版地址。


下载
--------

ldap3 可以在 https://pypi.python.org/pypi/ldap3 下载。 如果你使用支持 *wheel* 格式的包管理器，你可以获取一个通用格式的 *wheel* 包并且安装在任何被支持的python环境下。

安装
-------

运行 **pip install ldap3** 来安装ldap3。如果需要库文件的话，安装 ``pyasn1`` 这个包。 如果需要启用 Kerberos 支持，你需要安装 ``gssapi`` 。 ldap3包含了一个向后兼容的（从Python3.4.3开始）的 ``ssl.check_hosname`` 以用在旧版（<Python2.7.10）的Python上。如果你打算用到新版的 ``check_hostname`` 的一些特性的话，你需要安装backports.ssl_check_hostnames，这个包会随着Python的版本一直更新下去。
 


GIT 仓库
--------------

你可以从这个地址下载最新的源码 https://github.com/cannatag/ldap3/tree/master


对本项目作出贡献
-----------------------------

ldap3 的源代码托管在 github上，你可以通过fork https://github.com/cannatag/ldap3/dev 并提交 **pull request + 你的修改** 的方式来向本项目贡献代码。


持续集成
----------------------
持续集成的测试地址在这里： https://travis-ci.org/cannatag/ldap3


支持
-------

你可以在这里提交一个Support tickt: https://github.com/cannatag/ldap3/issues/new


联系我
----------

如果你要需获取更多信息或者给出建议，请发邮件到 cannatag@gmail.com。你也可以在https://github.com/cannatag/ldap3/issues/new 开一个open ticket 。


致谢
---------

* **Ilya Etingof**,  *pyasn1* 的作者，感谢他杰出的工作和支持。

* **Mark Lutz** 他的 *Learning Python* 和 *Programming Python* 丛书， **John Goerzen** 与
  **Brandon Rhodes** 共同编写的书 *Foundations of Python Network Programming* (第二版和第三版)。
  我学习python和开发次项目，多亏了他们的书。

* **JetBrains** ，他们向开源软件捐赠了杰出的IDE： *PyCharm 4 Professional*.

* **GitHub** 提供了 *免费的仓库空间和工具* 用来开发这个项目。

*  **Python Software Foundation** 提供了云基础架构用于测试。
