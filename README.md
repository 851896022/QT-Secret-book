
# QT武林秘籍——我在QT中遇到的那些坑

## (1)QUdpSocket接收数据
        进入槽后，要用这种方式读取，否则数据可能会导致不发readyRead()信号
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
        配合https://github.com/851896022/QLog
## (4)可以在pro文件中写上标记版本号+ico图标
        VERSION = 2019.08.08
        RC_ICONS = main.ico