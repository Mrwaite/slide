## 分享



---

## 前端性能优化清单 2017

- [Front-End Performance Checklist 2017](https://github.com/Mrwaite/Share/blob/master/Front-End%20Performance%20Checklist%202017_CN%20.md)

Note:
RAIL 是一种以用户为中心的性能模型,response,animation,idle,load，响应，动画，空闲，加载

---

### I Peeked Into My Node_Modules Directory And You Won’t Believe What Happened Next

- [原文](https://medium.com/friendship-dot-js/i-peeked-into-my-node-modules-directory-and-you-wont-believe-what-happened-next-b89f63d21558)

Note:
npm 仓库上存在大量质量参差不齐，年久失修的库，Node.js 的安全问题慢慢变得严峻起来

--

### About Node_Modules

- Express
- Ember
- Babel

--

### Express

- npm install => 291 installed modules
1. "yummy" 中包含 "like tweet.js"
2. a POST request to the twitter 
3. 给一条关于 Hot Pockets 的推文点赞 

Note:
想象一下，如果你吃早餐有291种成分。你会担心，不是吗？

-- 

### Ember

1. Glimmer 95KB
2. brittanica 93KB
3. term.json共计17,648行，描述以字母G开头的各种单词和短语。

Note:
Ember.js是一个JavaScript Web框架.Ember.js被gzip压缩后只有112KB，但是glimmer这个库大小为95KB，其中包含


--

### Bable-core

![babel-core](https://cdn-images-1.medium.com/max/1600/1*4UF6rEG73xHxcjDn5Abb3A.png)

Note:
Babel是下一代JavaScript的编译器.许多人抱怨其混乱的插件系统，过于复杂的配置文件和不清楚的错误消息.美国的餐馆老板，这么大面子，是不是赞助呢，不得而知。

--

- [浅谈 Node.js 安全](https://zhuanlan.zhihu.com/p/28105239)
- [node-serialize 模块安全问题](http://paper.seebug.org/221/)

Note:
饿了么大前端知乎周刊上的文章，主要是讲 HTTP 相关的一些安全问题。
本质上这是一个序列化 <—> 反序列化的过程，因为采用了 new Function()或者 eval作为反序列化的工具, 导致了任意代码执行，可以执行一些危险的远程代码。
大家尽量使用那些用户基数大的，有人经常维护的知名node库，npmjs上可以看到每周，每月的下载量。

--- 

#### 研表究明，汉字的序顺并不定一能影阅响读，比如当你看完这句话后，才发这现里的字全是都乱的。

Note:
请大家看一遍这段文字。
css有几个属性用来设置单词断行和换句，但是像中文/日文/韩文就不需要了。
请联系刚哥 gang.liu
slack支持#ecloud-support

--

#### 降临
![img](https://img3.doubanio.com/view/photo/raw/public/p2430415855.jpg)

Note:
中文和英文
外星人的语言被描述成一个摆脱了时间性／线性的存在。

--

- [关于语言，意识和记忆的呓语](https://movie.douban.com/review/8178580/)
- [萨丕尔-沃夫假说](https://zh.wikipedia.org/wiki/%E8%96%A9%E4%B8%95%E7%88%BE-%E6%B2%83%E5%A4%AB%E5%81%87%E8%AA%AA)



