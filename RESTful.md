# RESTful表征性状态转移
——————
* 资源与URI,资源被识别需要唯一标识(URI)

         URI设计应遵循可寻址性原则，具有描述性

* 统一资源接口

         任何资源通过使用相同的接口进行资源访问，使用标准HTTP方法，如GET、PUT、POST等
         
## GET

* 安全且幂等

* 获取表示，缓存

         200(ok) - 表示已在响应中发出
         
         204(无内容) - 资源有空 
         
         301(moved permanently) - 资源URI已被更新
         
         303(see other) - 其他(负载均衡)
         
         304(not modified) - 资源未更改(缓存)
         
         400(bad request) - 坏请求
         
         404(not found) - 资源不存在
         
         406(not acceptable) - 服务端不支持所需表示
         
         500 - 错误响应
         
         503(service unavailable) - 服务端无法处理请求
         
## POST
 
* 不安全，不幂等

* 创建子资源，部分更新资源

         200(ok) - 如果现有资源已被更改
         
         201(created) - 新资源被创建
         
