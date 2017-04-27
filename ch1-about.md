# 关于本手册
## 范围
本手册意在为debian发行版提供策略需求。包含了Debian archive文件的结构和内容以及操作系统的一些设计问题，同时也规定了包含在Debian发行版中的每一个包所必须要满足的技术上的要求。

本手册同样也描述了和创建Debian包相关的一些policy。但是它并不是一份描述如何打包的导览文件，也不用于描述打包系统的行为，而是尝试去定义一些开发者必须要了解的包管理系统的接口。

手册中的脚注仅用于提供信息，并不作为手册的一部分。

附录部分并非手册最必要的信息。详细说明可以查看附录A的附录介绍与范围。

在本手册规范中，使用必须（must）、应当（should）、可以（may）以及需要（required）、推荐（recommanded）和可选（optional）这些词用来来区分重要性。 那些不符合本手册要求但是却以must（或者required）提交的包将一律不被Debian发行版接受。 未经许可而以should（或者recommended)提交的包会被当作一个缺陷，Non-conformance with guidelines denoted by should (or recommended) will generally be considered a bug, but will not necessarily render a package unsuitable for distribution. 手册中设置为may (optional)的包为可选，依赖于维护者的判断。
 
这些分类与缺陷的严重程度大致对等：严重的serious（违反must或者required要求的）、轻微的minor、一般的normal、或者重要的important（违反should或者recommended要求的）以及希望改进的（optional类要求的）。 
 
即便是编译一个包用于其它的发布方式或者仅仅本地使用，本手册中的大部分内容也是非常有用的。
udebs (stripped-down binary packages used by the Debian Installer)可以不遵从本手册的要求。详细信息请查阅  Debian Installer internals manual 。

## 文档新版本
This manual is distributed via the Debian package debian-policy (packages.debian.org http://packages.debian.org/debian-policy). 

The current version of this document is also available from the Debian web mirrors at /doc/debian-policy/. ( www.debian.org http://www.debian.org/doc/debian-policy/) Also available from the same directory are several other formats: policy.html.tar.gz (http://www.debian.org/doc/debian-policy/policy.html.tar.gz), policy.pdf.gz (http://www.debian.org/doc/debian-policy/policy.pdf.gz) and policy.ps.gz (http://www.debian.org/doc/debian-policy/policy.ps.gz). 

The debian-policy package also includes the file upgrading-checklist.txt.gz which indicates policy changes between versions of this document. 

## 作者和维护者

本手册最初是由Ian Jackson于1996年编写的，当时的文档名字是"Debian GNU/Linux Policy Manual". 在1996年11月27日，由David A. Morris进行了修订。1997年3月15号， Christian Schwarz 添加了新的内容并于1997年4月到7月间进行了重构。 Christoph Lameter 贡献了 "Web Standard". Julian Gilbey 在2001年做了大规模重构。

从1998年9月开始， 本文由debian-policy mailiing list负责维护。任何一个在经过讨论并取得maillist共识后提议就会被添加到本手册。 针对本文档最终的编辑工作是由文档维护组进行。下面是当前的维护者：
Russ Allbery 
Bill Allombert 
Andrew McMillan 
Manoj Srivastava 
Colin Watson 

本文作者尽量避免笔误或者其他错误，但这种问题可能无法完全避免。如果发现有此类问题，或者有意见、建议、批评等，请发送邮件给debian-policy@lists.debian.org , 或者通过debian-policy包提交bug report。

请勿就本文的修改问题单独联系作者或者维护者本人。


## 相关文档资料
除了本手册外，还有其他的一些文档也有助于读者更好的理解Debian的一些策略和过程。

其他的“子策略”文档可参见: 
File System Structure, Section 9.1.1 
Virtual packages, Section 3.6 
Menus, Section 9.6 
Perl programs and modules, Section 11.9 
Prompting in maintainer scripts, Section 3.9.1 
Emacs lisp programs, Section 11.10 

此外，Debian开发者手册也提供了一些策略。这个文档向Debian的开发者描述开发过程以及一些资源，但是这部分并不规范，而是也包含了一些策略之外的内容，例如开发者最佳实践。

Debian开发者手册可以在developers-reference包里找到。您也可以从Debian网站的/doc/developers-reference/下找到。  
最后，Debian-policy包中使用和其他测试文档类似的方法维护了一份可机读的copyright文件。Use of this format is optional. 



# 术语定义
下面是本文档中涉及的一些术语定义: 

ASCII

由ANSI X3.4-1986及其后继版本所定义的一种字符编码规范，referred to in MIME as US-ASCII, 包含了unicode的前128个字符，每个字符占8位。and corresponding to an encoding in eight bits per character of the first 128 Unicode characters, with the eighth bit always zero. 

UTF-8

根据 RFC 3629定义的unicode转换格式（有时候也称为编码）. UTF-8将ASCII作为一个子集，因此任何ASCII编码的文字在UTF-8中都是有效的。 
