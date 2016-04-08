title: es6
date: 2016-03-07 14:35:11
tags: es6
---
------------------------------------------------
1.module
模块化

AMD(提前执行):
代表【require.js】

	define(['./a', './b'], function(a, b) { // 依赖必须一开始就写好
	a.doSomething()
	// ...
	b.doSomething()
	// ...
	})

CMD(延迟执行):CMD 推崇 as lazy as possible
代表【sea.js】

	define(function(require, exports, module) {
	var a = require('./a')
	a.doSomething()
	// ...
	var b = require('./b') // 依赖可以就近书写
	b.doSomething()
	// ...
	})

CommonJS:require() 与 exports

	// package/lib 是我们须要的一个依赖项
	var lib = require('package/lib');

	// 我们的模块的一些行为
	function foo(){
		lib.log('hello world!');
	}

	// 把 foo 导出（暴露）给其它模块
	exports.foo = foo;











