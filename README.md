# 软件开发最佳实践（伪）

本文档是是记录项目开发过程中遇到的问题和解决方法的记录，为其他项目开发过程作参考。

## 起因

笔者团队是由大学生和研究生组成的，跟随老师和研究生学长开发了一个项目。此前团队内并没有开发项目的经验，甲方也没有提供相应支持的经验，二者都是两眼一抹黑，最后导致整个项目的开发体验非常地稀碎。这种稀碎不只是甲方的问题，也有团队内部的问题，在开发中对我们双方都造成了很大的困扰。

在经历了比较折磨的开发流程后，我们终于是把产品交付了，在所有的后置工作都完成之后，在老师的建议下，我们决定对项目从需求分析到最终交付的全过程中所遇到的各种问题和收获合成一个文档，供老师和学长所在的研究团队的其他项目进行参考。

## 内容

正如上文所说，本文档中包含了我们项目开发过程中遇到的所有问题，同时也包含了在开发过程中我们不断地修正项目得到的经验。这些内容比较粗浅甚至可能包含了大量的错误，但我们还是选择将这些经验以文字的形式共享出来，一方面既是对自己的警示，也是为其他人提供一个参考，另一方面也希望对此类问题比较熟悉的大牛斧正该文档的内容。

___请注意：本文中并不会或只会有限的的包含对某些名词的一般性解释，主要是写我们粗浅的经验，故并不适合对项目开发或编码，设计等没有任何经验的同学查看或请结合其他资料进行理解。___

我们将这个文档分为了几个部分，分别是：

- 分析
- 设计
- 编码
- 测试
- 部署
- 杂项

每个部分都有一个或几个子项，基本涵盖了软件开发的全过程，谨供各位参考。

# Copyright

本文档的初版笔者是参与了软件开发的lony2003，kongqingxia，以及DymaticPro（TODO：问他Github昵称）编写，其他的贡献者请参考本文的Github页面。

同时本文档欢迎本科研团队的所有同学或老师参与完善，也欢迎其他同学、老师提出问题和修改意见。

本文开源在Github中并部署于Github Pages，感谢微软和Github给我们这个白嫖的机会 [doge]

本文遵循 [CC BY-NC-SA 4.0 （署名-非商业性使用-相同方式共享 4.0 国际）](https://creativecommons.org/licenses/by-nc-sa/4.0/) 协议开源，使用时请遵守相关条款。

Powered by [mdBook](https://rust-lang.github.io/mdBook/)
