 let socket = new WebSocket('ws://192.168.2.111:8078/websocket')

​    //打开事件

​    socket.onopen = function () {

​      console.log('Socket 已打开')

​      //socket.send("这是来自客户端的消息" + location.href + new Date());

​    }

 

​    //获得消息事件

​    socket.onmessage = (msg) => {

​      console.log(msg.data)

​      if (msg.data !== '连接成功') {

​	//将数据转为对象形式

​        let data = JSON.parse(msg.data)

​        console.log(data)

​        //发现消息进入    调后台获取

​      

​      }

​    }

 

​    //关闭事件

​    socket.onclose = function () {

​      console.log('Socket已关闭')

​    }

 

​    //发生了错误事件

​    socket.onerror = function () {

​      alert('Socket发生了错误')

​    }