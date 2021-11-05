.. _chatRoom:

1. 简易聊天室Chatting Room
############################

1.1 组成部分
**************************** 

1.1.1 Httpserver
++++++++++++++++++++++++++++ 

* 支持文件访问，流量访问， **index.html**
* 实现一个文件 *Servlet*

1.1.2 Websocket Server
+++++++++++++++++++++++++++

* 普通的 *http* 实现是按照周期性轮询，效率不高
* *websocket* 长连接，服务器可以主动推送数据，效率高

1.1.3 协议设计
+++++++++++++++++++++++++++

.. important::

    协议格式，json格式， {type:"协议类型", data: {}}

.. attention::

  * login协议。

    * Clinet: {type: "login_request", data: {"name": "nickname"}} 
    * Server: {type: "login_response", result: 200, msg: "ok"}

  * send协议。

    * Clinet: {type: "send_request", data: {"msg" : "message"}} 
    * Server: {type: "send_response", result: 200, msg: "ok"}


  * user_enter 通知 S->C

    * {type: "user_enter", msg : "xxx 加入聊天室"} 

  * user_leave 通知 S->C

    * {type: "user_leave", msg : "xxx 离开聊天室"} 

  * msg 通知

    * {type: "msg", msg : "massage details", user: "xxx", time: "xxxx"} 

简要协议规定如上所列。