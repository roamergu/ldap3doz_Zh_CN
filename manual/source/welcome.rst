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


ldap3允许发送一个空列表来创建一个GroupOfNames object，即使LDAPV3的官方架构里不允许这么干。

ldap3 allows communication over Unix sockets (ldapi:// scheme, LDAP over IPC) even if this is not required by any official LDAP RFCs.


PEP8 Compliance
---------------

ldap3 is PEP8 compliant, except for line length. PEP8 (https://www.python.org/dev/peps/pep-0008/) is the standard coding style
guide for the Python Standard Library and for many other Python projects. It provides a consistent way of writing code for maintainability
and readability following the principle that "software is more read then written".


Home Page
---------

The home page of the ldap3 project is https://github.com/cannatag/ldap3


Documentation
-------------

Documentation is available at http://ldap3.readthedocs.org. You can download a PDF copy of the manual at https://media.readthedocs.org/pdf/ldap3/stable/ldap3.pdf


Download
--------

The ldap3 package can be downloaded at https://pypi.python.org/pypi/ldap3. If you use a package manager that support the *wheel* format
you can get the universal wheel package, and install it on any supported Python environment.


Install
-------

Install with **pip install ldap3**. If needed the library installs the ``pyasn1`` package. If you need Kerberos support you must
install the ``gssapi`` package. ldap3 includes a backport (from Python 3.4.3) of ssl.check_hostnames to use on older
(< 2.7.10) Python version. If you want to use a newer version of the check_hostnames feature you can
install the ``backports.ssl_check_hostnames`` package that should be kept updated by its author with the latest Python release.


GIT repository
--------------

You can download the latest released source code at https://github.com/cannatag/ldap3/tree/master


Contribuiting to this project
-----------------------------

ldap3 source is hosted on github. You can contribute to the ldap3 project on https://github.com/cannatag/ldap3/dev
forking the project and submitting a *pull request+ with your modifications.


Continuous integration
----------------------

Continuous integration for testing is at https://travis-ci.org/cannatag/ldap3


Support
-------

You can submit support tickets on https://github.com/cannatag/ldap3/issues/new


Contact me
----------

For information and suggestions you can contact me at cannatag@gmail.com. You can also open a support ticket on
https://github.com/cannatag/ldap3/issues/new


Thanks to
---------

* **Ilya Etingof**, the author of the *pyasn1* package for his excellent work and support.

* **Mark Lutz** for his *Learning Python* and *Programming Python* excellent books series and **John Goerzen** and
  **Brandon Rhodes** for their books *Foundations of Python Network Programming* (Second and Third edition).
  These books are wonderful tools for learning Python and this project owes a lot to them.

* **JetBrains** for donating to this project the Open Source license of *PyCharm 4 Professional*.

* **GitHub** for providing the *free source repository space and tools* used to develop this project.

* The **Python Software Foundation** for supporting the cloud lab infrastructure used for testing the library.
