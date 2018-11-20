## 简介

疯狂编程10年，平均每天10小时以上，一周写代码80小时。技术经历和技术栈如下：

* j2ee（servlet、jsp、jdbc、spring、hibernate、struct2、osgi、设计模式、各种框架和自研框架）。
* 前端（css、html、js原生API包括ajax、早期库jquery、extjs、mootools、yui等）。
* js库实现css3选择器、动画引擎、兼容性事件处理。
* svn、git、nodejs、lisp、maven、mysql。
* 手游客户端（单机、网游、RPG、动作，策略、农场经营、跑酷、卡牌等）。
  * 私有引擎（java、c，2d，引擎、工具、游戏三层编写）。
  * cocos2dx（c++、lua，2d，纯c++和纯lua网游、cocos修改定制、游戏层框架）。
  * gameplay3d（c++、lua，3d，定制即时策略战斗）。
  * unity3d（c#，2d/3d，插件、游戏框架层）。
* 自研游戏引擎（c99、opengles3.x、java、swift，2d/3d）。
* unity3d插件、开箱即用gameplay框架、vulkan、metal（进行中）。
* 人工智能、区块链、操作系统内核（学习中）。
* .....

```
曾今乔布斯的Mac团队，衣服上印着: “我爱每周工作90小时。”    
作为回应，Lisa团队的印着: “一周工作70小时，但产品已经面世。”    
而AppleⅡ团队淡定地印着: “一周工作60小时——赚钱养活Lisa和Mac。”
```

## 社交网络

* 「微博」[分享有趣的见解和闪念（一句话纯文字）](https://weibo.com/scottcgi)
* 「知乎」[答题和专栏（同步技术和洞见思考）](https://www.zhihu.com/people/scott.cgi)
* 「豆瓣」[标记书籍和电影，日记（同步洞见思考）](https://www.douban.com/people/scottcgi)
* 「简书」[写作（同步技术和洞见思考）](https://www.jianshu.com/u/63a72cf6fff1)
* 「csdn」[纯技术分享（同步技术）](https://blog.csdn.net/tom_221x)
* 「GitHub」[代码项目](https://github.com/scottcgi)

所有的文章会随着信息的积累和认知的改变，而不断地修订（增删改），并会同步更新到不同的社交账号。

* 技术分享
  * [知乎专栏（又在写代码）](https://zhuanlan.zhihu.com/scottcgi0)
  * [简书文集（代码分类）](https://www.jianshu.com/u/63a72cf6fff1)
  * [csdn博客](https://blog.csdn.net/tom_221x)
* 洞见思考
  * [知乎专栏（闪念与乱想）](https://zhuanlan.zhihu.com/scottcgi)
  * [简书文集（闪念与乱想）](https://www.jianshu.com/nb/13094385)
  * [今日头条（图文并茂）](https://www.toutiao.com/c/user/105061320295/#mid=1613723709292557)
  * [豆瓣日记](https://www.douban.com/people/scottcgi/notes)
* 闪念
  * [微博](https://weibo.com/scottcgi)
  * [知乎想法](https://www.zhihu.com/people/scott.cgi/pins)
  
>不同平台不同的用户，平台提供流量和工具，创作者提供内容，平台与创作者合作的好就能共赢。没有流量就没有创作者，没有试错就没有迭代，流量来自于需求和解决用户痛点，但成功的平台往往是从抓住用户的本能开始的。当算法掌握了人们的需求，最终我们看到的就是被人工智能筛选出来的——人类本能，以及人类智能与本能的博弈。


## 开源项目 

* [Mojoc](https://github.com/scottcgi/Mojoc) 自研游戏引擎（c99，opengles3.x，android/ios）。

  纯c的游戏引擎，未来会扩展到windows和mac平台，并会给渲染层添加vulkan和metal接口。接下来一些构想：
  * 在渲染层之上构建一个跨平台的UI库（使用渲染层，或是封装统一的平台绘制层）。
  * 在UI库之上开发各种编辑器或是软件。
  * 剥离出一个跨平台的c语言工具库，就像jdk一样的cdk框架。
  * 使用cdk实现一个脚本语言MojoScript——lua的改进版本，然后完成高层逻辑抽象。一些早期的设计概念：
    1. 函数具有变量的特性，可以在函数中创建函数。
    1. 无类型声明变量，所有的变量都是指针类型，包括基本类型数值。
    1. 支持协程和闭包。
    1. json为语言内在的支持，成为语言内在的构建方式。
    1. 无法继承没有全局变量，跨页面访问变量需要明确导入导出操作。
    1. 运算符操作直接用映射到本地代码。
    1. 所有的一切都看成求值，求值类型相同的放到一起计算，根据优先级，进行计算。
    1. 不使用模拟指令。
    1. 代码解析后，没有二进制数据，直接翻译成本地代码的数据结构。
    1. 按照分号结尾的语句翻译为本地代码，把语句抽象成多个最小单位求值表达式的组合，执行语句就是对表达式求值。
  * 使用cdk自举一个c的编译器。
  * 重写c标准库实现。
  * c实现操作系统内核。
  
* [MojoJS](https://github.com/scottcgi/MojoJS) 使用js实现了css3选择器、动画引擎、兼容性事件处理。

  这个项目使用业余时间在2009年完成，开始托管在google code上，后来放到github上就一直没有维护了。未来会把动画引擎继续完善做好，并加入webgl、asm.js、WebAssembly的支持。另外，会以模块形式开发，解决特定的痛点，做到小而美、开箱即用毫无负担（心理、理解、使用、性能、冗余）。
  
* [MojoUnityJson](https://github.com/scottcgi/MojoUnityJson) c#的json解析器。
  
  从u3d的游戏框架中剥离出来的




>编程10年后，想的比写的多，想好了就会写的很快。认识到编程不是目的而是过程，不再挑剔编程语言，不再害怕或排斥不熟悉的技术，更不会心有余悸，而是荣辱不惊。与代码洁癖和谐相处并合作愉快，并适应各种语法格式，没有喜好与抱怨——按部就班的把思想平静地编程现实。
>
>明白没有完美——缺陷是来自于路径依赖，宇宙熵增推动着高效与混乱的转换，存在未必合理可能只是在消亡的路上。可以用代码流畅的表达想法、抽象逻辑、映射客观、架构因果、尽情地改进与迭代。发现心中没有规则与限制，就可以断点调试现实的坚硬与黑暗。
>
>人生很短，编程的道路却很长，要学习的还有很多，未来已经蜿蜒到看不到尽头的远方，我独自在黑屋子里与递归为伴，感受着毁灭后的重建，推到重来就是人生无法逃避的循环。
 
