# 如何在windows 10 配置gzip

## 问题

在硬盘上有几个T的bam格式文件，需要上传到服务器，如果直接上传会浪费空间与时间，因此借鉴linux系统上的gzip方法对文件进行压缩，可以节省空间

## 步骤

### 下载gzip文件

- 下载链接：[https://gnuwin32.sourceforge.net/packages/gzip.htm](https://gnuwin32.sourceforge.net/packages/gzip.htm)
- 选择其中的Binaries文件下载到本地并解压，然后复制bin文件夹所在的地址（不包含bin文件夹名称）

### 配置路径

- Win键 + E，找到“此电脑” or “我的电脑”
- 右键点击，选择“属性”，选择“高级系统设置”

![Untitled](%E5%A6%82%E4%BD%95%E5%9C%A8windows%2010%20%E9%85%8D%E7%BD%AEgzip%2047b6d5e18e1f44d4a1b9b46484887eec/Untitled.png)

- 选择”高级“——“环境变量”

![Untitled](%E5%A6%82%E4%BD%95%E5%9C%A8windows%2010%20%E9%85%8D%E7%BD%AEgzip%2047b6d5e18e1f44d4a1b9b46484887eec/Untitled%201.png)

- 点击系统变量下面的”新建“——弹出窗口，第一个输入‘GZIP’，第二个输入复制的bin文件所在路径——“确定”
- 点击系统变量中的PATH——“编辑”——弹出窗口，“编辑文本”

![Untitled](%E5%A6%82%E4%BD%95%E5%9C%A8windows%2010%20%E9%85%8D%E7%BD%AEgzip%2047b6d5e18e1f44d4a1b9b46484887eec/Untitled%202.png)

- 在弹出的窗口输入：%GZIP%\bin;——输入完毕“确定”
    - 英文字符
    - 使用；隔开其他的变量

### 使用

- 在需要压缩文件的目录下打开cmd
- gzip -h查看说明，以及验证是否配置成功
- gzip 文件名 用于压缩文件
- gzip -r 文件夹名 用于压缩文件夹内的文件
    - 有可能会输出permission denied，但是不用管它，压缩已经在进行了