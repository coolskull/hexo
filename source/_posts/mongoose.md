title: mongoose
date: 2016-03-29 16:48:04
tags:
---
------------------------------------------------
 1.先了解mongo(no-sql数据库的特点)
    链接：[我的mongo教程](http:)
 2.ES6Promise使用
     链接：~~[我的promise教程](http:)~~
             [promise nodejs教程](https://www.promisejs.org/)
    var promise = Meetups.find({ tags: 'javascript' }).select('_id').exec();
	promise.then(function (meetups) {
	  var ids = meetups.map(function (m) {
		return m._id;
	  });
	  return People.find({ meetups: { $in: ids }).exec();
	}).then(function (people) {
	  if (people.length > 10000) {
		throw new Error('Too few people!!!');
	  } else {
		throw new Error('Still need more people!!!');
	  }
	}).then(null, function (err) {
	  assert.ok(err instanceof Error);
	});