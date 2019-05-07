对于不同的实现，异常处理也不同：

1. callback style 中要将错误处理放在回调函数中进行
1. promise 要注意是外层 catch() 还是内层 catch()
1. async 实际上是将异步处理写成同步的样子，需要用 try/catch 进行处理
