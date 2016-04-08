title: zTree入门到精通（1）
date: 2016-02-05 14:26:00
tags: [ztree,编程]
---

    <!DOCTYPE html>
    <html>
    <head lang="zh-cn">
        <meta charset="UTF-8">
        <title></title>
        <link rel="stylesheet" href="ztree/css/zTreeStyle/zTreeStyle.css"/>
        <script type="text/javascript" src="jquery/jquery.js"></script>
        <script type="text/javascript" src="ztree/js/jquery.ztree.all-3.5.js"></script>
        <script>
            $(function () {
                var data = [
                    {"id": 0, "name": "根节点"},
                    {"id": 1, "name": "节点1", "pid": 0},
                    {"id": 2, "name": "节点2", "pid": 0},
                    {"id": 3, "name": "节点3", "pid": 0},
                    {"id": 4, "name": "节点4", "pid": 0},
                    {"id": 21, "name": "节点21", "pid": 2},
                    {"id": 22, "name": "节点22", "pid": 2},
                    {"id": 23, "name": "节点23", "pid": 2}
                ];
                   var setting = {
                       data: {
                           simpleData: {
                               enable: true,    //  默认为false，设置为true的时候才可以使用简单数据格式。
                               idKey: "id",       // 节点数据中保存唯一标识的属性名称：对应data里面的id。
                               pIdKey: "pid",   // 节点数据中保存其父节点唯一标识的属性名称：对应data里面的pid。
                               rootPid: 0         // 用于修正根节点父节点数据，即 pIdKey 指定的属性值。
                         }
                     }
                 };
                var zTree = $.fn.zTree.init($("#tree"), setting, data);
                zTree.expandAll(true);  // 展开全部节点
            });
        </script>
    </head>
    <body>
    <div id="tree"></div>
    </body>
    </html>

 1.使用上面的代码之后，你会发现添加了jquery、css、js  ，树还是不能正常显示，你需要：

    <div id="tree"></div>

添加class，改成下面这样：

    <div id="tree" class="ztree"></div>


