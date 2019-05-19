# 消息队列

## 使用场景

### 1. 异步处理

   >串行
   
   ![](https://github.com/vicjiafeng/html_study/blob/master/image/chuanxing.png)
   
     
   >并行
   
   ![](https://github.com/vicjiafeng/html_study/blob/master/image/bingxing.png)
     
  
   >引入消息队列
   
   ![](https://github.com/vicjiafeng/html_study/blob/master/image/1.png)


### 2. 应用解耦（订单-库存）

   >![](https://github.com/vicjiafeng/html_study/blob/master/image/2.png)

### 3. 流量削锋（秒杀）

   >![](https://github.com/vicjiafeng/html_study/blob/master/image/3.png)
   
  
  * 请求先入消息队列，而不是由业务处理系统直接处理，做了一次缓冲,极大地减少了业务处理系统的压力
   
  * 队列长度可以做限制，事实上，秒杀时，后入队列的用户无法秒杀到商品，这些请求可以直接被抛弃，返回活动已结束或商品已售完信息
   
### 4. 日志处理（kafka应用）

  * 将消息队列用在日志处理中，比如Kafka的应用，解决大量日志传输的问题
  
   

## 两种模式

### 1. 点对点
  
  * 每个消息只有一个接收者（Consumer）(即一旦被消费，消息就不再在消息队列中)
  
  * 发送者和接收者间没有依赖性，发送者发送消息之后，不管有没有接收者在运行，都不会影响到发送者下次发送消息
  
  * 接收者在成功接收消息之后需向队列应答成功，以便消息队列删除当前接收的消息

### 2. 发布/订阅
  
  * 每个消息可以有多个订阅者
  
  * 布者和订阅者之间有时间上的依赖性。针对某个主题（Topic）的订阅者，它必须创建一个订阅者之后，才能消费发布者的消息
  
  * 为了消费消息，订阅者需要提前订阅该角色主题，并保持在线运行
