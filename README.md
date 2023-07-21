# HuggingFace部署签名服务

对接go-cqhttp

优点：不需要服务器搭建，白嫖Huggingface的2核16G服务器，一键克隆即可运行，一人一地址，避免公共使用导致集体封号

缺点：移动网络无法访问HuggingFace

## 第一步：克隆空间

打开我已经部署好的空间：[QQsign](https://huggingface.co/spaces/CikeyQI/QQsign)，点击右上角三个点，点击**Duplicate this Space**
![克隆空间](https://img-blog.csdnimg.cn/67fdeed3858c48d7858e79410e1ba0a3.png)

## 第二步：填写相应的项

 **TXLIB_VERSION：**
 
 本项请直接填写版本号即可，如`8.9.63`，不用填写路径！存放核心so文件的文件夹绝对路径，在本空间已经存放了官方提供的最近六个版本的so文件，包括`8.9.50` `8.9.58`或`8.9.63`，支持的所有版本号在txlib目录下，推荐使用高于8.9.50及以上的版本，您可以自行将so文件上传到空间的txlib文件夹中，选择自己的版本

填写好后，点击**Duplicate this Space**，将自动部署

## 第三步：获取地址

当状态变成**Running**时，即部署成功

![空间开始运行](https://img-blog.csdnimg.cn/4864f13caff1466d982b91023b91da56.png)

点击右上角三个点，选择**Embed this Space**

![查看个人URL](https://img-blog.csdnimg.cn/bf7fc6cf3ab94290bdee765660ca5cf9.png)

下方Direct URL就是你的接口地址，点**copy**复制到剪切板

![查看个人URL](https://img-blog.csdnimg.cn/3b310c17ebb0496aac36a4ef40d0c8ee.png)

## 第四步：填写并使用

打开config.yml
![](https://alancn.gitee.io/post-images/1689269641506.png)

找到sign-server
![](https://alancn.gitee.io/post-images/1689269645293.png)

此处为你复制的地址+/sign?key=114514 

```plaintext
sign-server: 'URL/sign?key=114514 '
#注意 server:  此冒号右边需要加上一次空格
#也可复制我的格式，替换URL即可
```

视频教程:https://www.bilibili.com/video/BV1yu4y1S7Zq/?share_source=copy_web&vd_source=10e97efb91b3a775e5b83c27743a2ada
