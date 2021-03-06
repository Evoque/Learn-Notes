## CO

### 前述

读ruanyf 的ES6的时候，知道了`co`这个用于任务执行的`flow-control`模块，本着彻底掌握`generator or GeneratorFunction runner`的目标，再加上其作者是大神[tj](https://github.com/tj)， 就把读[co](https://github.com/tj/co)源码加到了自己的list上了。



### 正文

`co`仅仅作为一个`generator`执行器模块，代码量并不多， 去除各种注释、空格、辅助函数， 核心代码只有几十行；但是由于中间条件判断比较多(各种对象类型的判断、转换)， 以及一些方法之间的循环引用， 递归调用，所以刚开始的调试和通读都没有完全掌握。

由于早就开始用`async await`， 所以对`generator`执行器的原理也都比较清楚，这次看`co`的主要目的是想学习大神的代码以及实现思路；所以比较关注代码细节。 

尝试了调试和通读， 效果都不太好，因为总是看了后面的忘了前面的，有种朦胧没掌握全的感觉。 所以尝试换一种方法：画图； 撸串之后花了大概两小时， 有如下的成果。

![co调用关系](C:\Users\wushuai\Desktop\co\imgs\数据中心.svg)





完工之后， 茅塞顿开、豁然开朗、彻底通透之类的感觉，果然来了。 各个func的调用关系、实现方式，几乎可以说是了如指掌。 虽然个别的细节不太赞同，或者说不太明白作者的意图， 不过和整体的模块功能及实现效果项目，有些微不足道，就不细扣了。 

几点收获：

- 思路清晰：虽然这只是个模块，远谈不上`framework`或者架构， 但是对掌握全局脉络真的非常有用。 几乎可以说， 画完之后可以是完全掌握了；

- 明确测试的重要性：每个成熟的第三方库，它的测试用例都要比真正的源码大几倍，有的是好几倍。 涵盖了类库必须要涉及甚至不会用到但是符合原理的刁钻用法。 

  > SO, 测试是一门学问， 也是保证代码功能至关重要的一环。







### 最后

其实这不能算一篇博文，不能计算到自己的OKR里面去。 先滥竽充数占个坑， 以后有好的内容再做补充吧。 































