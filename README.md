
# QT武林秘籍——我在QT中遇到的那些坑

## （1）QUdpSocket接收数据
        进入槽后，要用如下这种方式读取
            while(udpSocket->bytesAvailable())
        {
        }