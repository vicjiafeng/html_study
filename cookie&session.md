## cookie技术-客户端

* 储存在用户本地终端上的数据
* 客户端状态管理，辨别身份，进行session追踪
* 记录访问者的基本信息

## session技术-服务器端

* 服务器端状态管理
* session基于cookie技术，当浏览器访问服务器时，服务器会建立一个session对象(包含session ID)，
  服务器默认情况下将id以cookie方式发给浏览器，浏览器将session ID 保存在内存中，当再次访问，会将session ID发给服务器，
  服务器依照id找到session对象
