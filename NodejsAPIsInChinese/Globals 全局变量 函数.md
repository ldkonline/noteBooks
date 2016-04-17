#全局对象#
这些对象在所有的模块中都可以使用。这些对象中的某些其实并不属于全局对象的作用域而是模块的作用域。文档中会对这些对象进行标注。

##Class:Buffer

- {Function}

用来处理二进制数据，请看[Buffer章节](https://nodejs.org/dist/latest-v5.x/docs/api/buffer.html)

##__dirname##

- {String}

当前正在执行的脚本所在的目录名称。

例子：在`/Users/mjr`中运行`node example.js`

```js
  console.log(__dirname);
  // /Users/mjr
  
``` 

`__dirname`更像是每个模块的本地变量而不是真正意义上的全局对象

比如说，有两个模块`a`和`b`,`b`依赖于`a`。目录结构如下

- `/Users/mjr/app/a.js`
- `/Users/mjr/app/node_modules/b/b.js`

`b`中的`__dirname`是`/Users/mjr/app/node_modules/b`,而`a`中的`__dirname`是`/Users/mjr/app`

##__filename##

- {String}

正在执行的文件的文件名。这是源码文件的绝对路径。对于一个主程序来说命令行中的名称不必与`__filename`一致。模块中的`__filename`值就是该模块的路径。

例如：在`/Users/mjr`中运行`node example.js`

```js
  console.log(__filename);
  // /User/mjr/examples.js
```

`__filename`更像是每个模块的本地变量而不是真正意义上的全局对象

##clearImmediate(immediateObject)##

请看[clearImmediate](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html#timers_clearimmediate_immediateobject) 在[timers](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)中的描述

##clearInterval(intervalObject)##

请看[clearInterval](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html#timers_clearinterval_intervalobject)在[timers](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)中的描述

##clearTimeout##

请看[clearTimeout](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html#timers_cleartimeout_timeoutobject)在[timers](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)中的描述

##console##

- {Object}

用来打印信息到stdout或者stderr。请看[console](https://nodejs.org/dist/latest-v5.x/docs/api/console.html)章节


##exports##

对`module.exports`的引用。请看[module system documentation](https://nodejs.org/dist/latest-v5.x/docs/api/modules.html)查看什么时候应该使用`exports`以及什么时候应使用`module.exports`。

`exports`更像是每个模块的本地变量而不是真正意义上的全局对象

请查看[module system documentation](https://nodejs.org/dist/latest-v5.x/docs/api/modules.html)获取更多信息

##global##

- {Object} 全局命名空间对象

在浏览器中最高级别的作用域就是全局作用域。意味着，在全局作用域中`var something`将会定义一个全局变量。在Node.js中却不是这样——做高级别的作用域并不是全局作用域；在Node.js模块中  `var something` 创建的是该模块的本地变量。

##module##

- {Object}

对当前模块的引用。一般来说，`module.exports`是用来定义一个模块的输出并且通过`require()`可以被其他模块使用。

`module`更像是每个模块的本地变量而不是真正意义上的全局对象

请查看[module system documentation](https://nodejs.org/dist/latest-v5.x/docs/api/modules.html)获取更多信息


##process##

- {Object}

进程对象。查看[process object](https://nodejs.org/dist/latest-v5.x/docs/api/process.html#process_process)章节

##require()##

- {Function}

引用模块。请看[Module](https://nodejs.org/dist/latest-v5.x/docs/api/modules.html#modules_modules)章节。`require`更像是每个模块的本地变量而不是真正意义上的全局对象


###require.cache###

- < Object>

当模块被引入的时候回缓存在这个对象中。从此对象中删除键值，下一个`require`将会重新加载这个模块。

###require.resolve()###

使用内部的`require()`机制定位一个模块。只会返回该模块的`__filename`而不引入该模块

##setImmediate(callback[,arg][, ...])##

请看[timer](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)

##setInterval(callback,dalay[,arg][, ...])##

请看[timer](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)

##setTimeout(callback,dalay[,arg][, ...])

请看[timer](https://nodejs.org/dist/latest-v5.x/docs/api/timers.html)