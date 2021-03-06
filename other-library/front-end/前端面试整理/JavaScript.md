JavaScript 初稿
===

> Create by **jsliang** on **2020-04-11 13:42:03**  
> Recently revised in **2020-04-11 13:54:37**

## <a name="chapter-one" id="chapter-one"></a>一 目录

**不折腾的前端，和咸鱼有什么区别**

| 目录 |
| --- | 
| [一 目录](#chapter-one) | 
| <a name="catalog-chapter-two" id="catalog-chapter-two"></a>[二 前言](#chapter-two) |

## <a name="chapter-two" id="chapter-two"></a>二 前言

> [返回目录](#chapter-one)

开始准备面试，瞎写写东西~

## <a name="chapter-three" id="chapter-three"></a>三 瞎写开始

> [返回目录](#chapter-one)

### 变量污染：编写块

问 1：在以下代码中，会输出什么？

```js
for (var i = 0; i < 3; i++) {}
console.log(i);
```

答：输出 3。

问 2：请在不使用 `let` 的情形下，解决 `i` 的变量污染

答：立即执行函数形成块作用域：

```js
(function() {
  for (var i = 0; i < 3; i++) {}
})()
try {
  console.log(i);
} catch (error) {
  console.log('i 不存在');
}
```

### 变量污染：优化解决

请说出下面代码打印内容，并进行优化

```js
for (var i = 0; i < 3; i++) {
  setTimeout(() => {
    console.log(i);
  }, 100);
}
```

答：3 3 3

* 优化 1：立即执行函数

```js
for (var i = 0; i < 3; i++) {
  (function(i) {
    setTimeout(() => {
      console.log(i);
    }, 100);
  })(i)
}
```

* 优化 2：let 

```js
for (let i = 0; i < 3; i++) {
  setTimeout(() => {
    console.log(i);
  });
}
```

---

**不折腾的前端，和咸鱼有什么区别！**

![图](../../../public-repertory/img/z-index-small.png)

**jsliang** 会每天更新一道 LeetCode 题解，从而帮助小伙伴们夯实原生 JS 基础，了解与学习算法与数据结构。

**浪子神剑** 会每天更新面试题，以面试题为驱动来带动大家学习，坚持每天学习与思考，每天进步一点！

扫描上方二维码，关注 **jsliang** 的公众号（左）和 **浪子神剑** 的公众号（右），让我们一起折腾！

> <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">jsliang 的文档库</span> 由 <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/LiangJunrong/document-library" property="cc:attributionName" rel="cc:attributionURL">梁峻荣</a> 采用 <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">知识共享 署名-非商业性使用-相同方式共享 4.0 国际 许可协议</a>进行许可。<br />基于<a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/LiangJunrong/document-library" rel="dct:source">https://github.com/LiangJunrong/document-library</a>上的作品创作。<br />本许可协议授权之外的使用权限可以从 <a xmlns:cc="http://creativecommons.org/ns#" href="https://creativecommons.org/licenses/by-nc-sa/2.5/cn/" rel="cc:morePermissions">https://creativecommons.org/licenses/by-nc-sa/2.5/cn/</a> 处获得。