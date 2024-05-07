# Peer之间的`Block`同步流程

* blockchain的update
    ![pic/sync01.png](pic/sync01.png)
    * blockchain的update自己就是一个goroutine
    ![pic/sync01.png](pic/sync02.png)

* 和downloader的`Block`同步交互
    * 在InsertChain里面加上断点
        ![pic/sync02.png](pic/sync03.png)
    * 可以看到在downloader里面调用了blockchain的`InsertChain`函数
        ![pic/sync03.png](pic/sync04.png)

* blockchain在eth和downloader里面通过config共享同一个对象。
    ![pic/sync04.png](pic/sync05.png)
    