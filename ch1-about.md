
# 范围
本手册意在为debian发行版提供策略需求。包含了Debian archive文件的结构和内容以及操作系统的一些设计问题，同时也规定了包含在Debian发行版中的每一个包所必须要满足的技术上的要求。

本手册同样也描述了和创建Debian包相关的一些policy。但是它并不是一份描述如何打包的导览文件，也不用于描述打包系统的行为，而是尝试去定义一些开发者必须要了解的包管理系统的接口。

手册中的脚注仅用于提供信息，并不作为手册的一部分。

附录部分并非手册最必要的信息。详细说明可以查看附录A的附录介绍与范围。

在本手册规范中，使用必须（must）、应当（should）、可以（may）以及需要（required）、推荐（recommanded）和可选（optional）这些词用来来区分重要性。 那些不符合本手册要求但是却以must（或者required）提交的包将一律不被Debian发行版接受。 未经许可而以should（或者recommended)提交的包会被当作一个缺陷，Non-conformance with guidelines denoted by should (or recommended) will generally be considered a bug, but will not necessarily render a package unsuitable for distribution. 手册中设置为may (optional)的包为可选，依赖于维护者的判断。
 
这些分类与缺陷的严重程度大致对等：严重的serious（违反must或者required要求的）、轻微的minor、一般的normal、或者重要的important（违反should或者recommended要求的）以及希望改进的（optional类要求的）。 
 
即便是编译一个包用于其它的发布方式或者仅仅本地使用，本手册中的大部分内容也是非常有用的。
udebs (stripped-down binary packages used by the Debian Installer)可以不遵从本手册的要求。详细信息请查阅  Debian Installer internals manual 。

# 文档新版本
This manual is distributed via the Debian package debian-policy (packages.debian.org http://packages.debian.org/debian-policy). 

The current version of this document is also available from the Debian web mirrors at /doc/debian-policy/. ( www.debian.org http://www.debian.org/doc/debian-policy/) Also available from the same directory are several other formats: policy.html.tar.gz (http://www.debian.org/doc/debian-policy/policy.html.tar.gz), policy.pdf.gz (http://www.debian.org/doc/debian-policy/policy.pdf.gz) and policy.ps.gz (http://www.debian.org/doc/debian-policy/policy.ps.gz). 

The debian-policy package also includes the file upgrading-checklist.txt.gz which indicates policy changes between versions of this document. 

# 作者和维护者



# 相关文档资料


# 术语定义
下面是本文档中涉及的一些术语定义: 

ASCII

由ANSI X3.4-1986及其后继版本所定义的一种字符编码规范，referred to in MIME as US-ASCII, 包含了unicode的前128个字符，每个字符占8位。and corresponding to an encoding in eight bits per character of the first 128 Unicode characters, with the eighth bit always zero. 

UTF-8

根据 RFC 3629定义的unicode转换格式（有时候也称为编码）. UTF-8将ASCII作为一个子集，因此任何ASCII编码的文字在UTF-8中都是有效的。 
