
# QT武林秘籍——我在QT中遇到的那些坑

## (1)QUdpSocket接收数据
        进入槽后，要用这种方式读取，否则可能会导致不发readyRead()信号
        while(udpSocket->bytesAvailable())
        {
            udpSocket->readDatagram(ch,size);
        }
## (2)QTcpSocket删除
        一定要用deleteLater
        一定要用deleteLater
        一定要用deleteLater
        否则会导致用户对象溢出
## (3)运行文件附带调试输出窗口
        CONFIG += console pro
        配合->http://github.com/851896022/QLog
## (4)可以在pro文件中写上标记版本号+ico图标
        VERSION = 2019.08.08
        RC_ICONS = main.ico
## (5)解决socket传输后等中文乱码
        转成base64传输
        QByteArray(QString.toStdString().data()).toBase64()
## (6)QT连接MySql后，长时间无操作（默认8小时）会断开。
        isOpen()等函数无法判断，需执行sql语句才能发现失败
        QSqlDatabase.setConnectOptions("MYSQL_OPT_RECONNECT=1");
        ↑断开后可自动重连
## (7)在槽使用sender()函数可获取到发出信号的对象的指针。

        
