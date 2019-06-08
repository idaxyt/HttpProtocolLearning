## HttpProtocolLearning

### HTTP发展历史
* HTTP0.9
  * 只有GET命令
  * 无Header
  * 服务端发送完，关闭TCP连接
* HTTP1.0
  * 有GET等命令
  * 有Status Code和Header等
  * 服务端发送完，关闭TCP连接
  * 多字符集支持，多部分发送、权限、缓存等
* HTTP1.1
  * 持久连接（同一个TCP连接发送相应多个请求）
  * pipeline（客户端发送多个请求，服务端按顺序相应）
  * 增加host和其它命令（host区分同一个物理服务器/集群部署的多个web服务）
* HTTP2.0
  * 所有数据二进制（以帧）传输
  * 同一个TCP连接中，服务端无需按顺序相应请求
  * 头信息压缩及服务端推送等提高效率的功能

### TCP三次握手
* 前提：HTTP只有请求/相应报文，报文传输通过TCP连接
* 说明：三次握手是保证网络传输时，客户服务之间的连接有效性。若第一客户端发送请求，服务端就返回内容，但由于网络原因未抵达客户端，
       且客户端发起请求的端口连接超时主动关闭连接状态，此时服务端并不知晓，一直处于开启连接状态，造成资源浪费。