# HuggingFace部署签名服务

对接go-cqhttp

优点：不需要服务器搭建，白嫖Huggingface的2核16G服务器，一键克隆即可运行，一人一地址，避免公共使用导致集体封号

缺点：移动网络无法访问HuggingFace

## 第一步：克隆空间

打开我已经部署好的空间：[QQsign](https://huggingface.co/spaces/CikeyQI/QQsign)，点击右上角三个点，点击**Duplicate this Space**
![克隆空间](https://img-blog.csdnimg.cn/67fdeed3858c48d7858e79410e1ba0a3.png)

## 第二步：填写相应的项

 **Visibility：**
 
 修改为Public，一定要公开，否则无法正常访问接口
 
 **COUNT：**
 
 Unidbg实例数量 ，官方建议等于核心数，免费空间是2核16GB，所以这里建议填`2`。（数值越大并发能力越强，内存占用越大）
 
 **TXLIB_VERSION：**
 
 本项请直接填写版本号即可，如`8.9.63`，不用填写路径！存放核心so文件的文件夹绝对路径，在本空间已经存放了官方提供的最近六个版本的so文件，包括`8.9.50` `8.9.58`或`8.9.63`，支持的所有版本号在txlib目录下，推荐使用高于8.9.50及以上的版本，您可以自行将so文件上传到空间的txlib文件夹中，选择自己的版本
 
![so文件存放路径](https://i.postimg.cc/jSDtXcVd/version.png)

**ANDROID_ID：**

打开go-cqhttp→device.json
![](https://alancn.gitee.io/post-images/1689270030213.png)
如果不是这个界面，可以按下CTRL+shift+F

填写好后，点击**Duplicate this Space**，将自动部署

![开始部署](https://img-blog.csdnimg.cn/121ba7ea6c124d91966ffd5131b30c69.png)

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

此处为你复制的地址+/sign     
