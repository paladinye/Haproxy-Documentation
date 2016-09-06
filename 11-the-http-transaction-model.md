HTTP协议是transaction-driven(事务驱动).  
一个request会且仅会产生一个response.

####1.传统模式，我们称之为"http close"
该模式下，客户端到服务器建立一个TCP连接，request被客户端在这个连接上传送，服务器返回response并关闭该连接.  
新的request 关联新的response

```
 [CON1] [REQ1] ... [RESP1] [CLO1] [CON2] [REQ2] ... [RESP2] [CLO2] ...
```

http连接数与http transaction一致。连接由服务器负责关闭，客户端不需要知道内容长度。

####2."keep-alive"模式
该模式基于http协议的事务性特征，改善"http close"模式以避免关闭两个相关的事务连接。该模式下，服务器为每个response强制指明内容长度以避免client无限期等待。该模式下会插入头部信息"Content-length"
```
[CON] [REQ1] ... [RESP1] [REQ2] ... [RESP2] [CLO] ...
```
该模式的优势表现在，
- 减少相关事务的处理延迟
- 服务器端更少的处理消耗

通常其效率高于“http close”，但也不是绝对，比如客户端常常限制其并发连接数。

####3.pipelining 模式
该模式改善了通信过程。其仍然使用"keep-alive",但是客户端不必等待上一个response再直接发送下一个request.在拉取包含大量图片的页面场景下相当有用。  
```
[CON] [REQ1] [REQ2] ... [RESP1] [RESP2] [CLO] ...
```
该模式消除了相关request之间网络延迟带来的的影响，极大的提高其性能表现。  
但是由于很多客户端无法将两个相关的request和response联系起来，无法正常使用该模式，所以强制服务器按与request相关的请求顺序进行回应。
> http 1.1 默认使用keep-alive模式，pipelinling需要在http client里面指定。  

默认情况下，haproxy针对持久性连接是工作在keep-alive模式下：每个连接的request和response都会被处理，每个response结束之后和新request发起之前，该连接会处于idle状态。
haproxy 支持5中连接模式：
- keep alive: 所有的request和response被正常处理
- tunnel: 只有第一个request和response被处理，其他直接转发
- passive close: request和response都会被加入"Connection: close"
- server close: 面向服务器的连接在发送response之后被关闭
- forced close: 在发送response之后连接被主动关闭  

[详细的说明参考haproxy相关配置选项](/1quick-reminder-about-http.html)
