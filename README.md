# util_storage
localStorage 兼容IE 等


### [功能描述]
给不支持本地存储的浏览器创建一个 window.localStorage 对象来提供类似接口


#### 该对象支持以下方法或属性
- setItem : function(key, value)
- getItem : function(key)
- removeItem : function(key)
- clear : function()
- length : int
- key : function(i)
- isVirtualObject : true

#### 二次包装的接口 window.LS 提供以下方法和属性（如果有jQuery则同样会扩展该对象），推荐使用
- set : function(key, vlaue)
- get : function(key)
- remove : function(key)
- clear : function()
- each : function(callback) callback接受两个参数 key 和 value
- obj : function() 返回一个对象描述的localStorage副本
- length : int

### [已知问题、使用限制]
* 原生本地存储的key是区分大小写的，模拟对象不区分（因为userData不区分key的大小写）
* 模拟对象的 clear 方法仅仅能清理通过本组件设定的数据
* 模拟对象的实际的存储容量跟原生本地存储有差异
* 模拟对象不支持任何localStorage事件件