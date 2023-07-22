# qqsign
# HuggingFace部署签名
对接go-cqhttp

白嫖Huggingface的2核16G服务器，一键克隆即可运行，一人一地址，避免公共使用导致集体封号

## 第一步：克隆空间

打开已经部署好的空间：[https://huggingface.co/spaces/link77/QQsign](https://huggingface.co/spaces/link77/QQsign)，点击右上角三个点，点击**Duplicate this Space**

## 第二步：填写相应的项

 **Visibility：**
 
 修改为Public，一定要公开，否则无法正常访问接口
 
 **COUNT：**
 
这里建议填`2`。
 
 **TXLIB_VERSION：**
 
 填写版本号，如`8.9.63`，不用填写路径！存放核心so文件的文件夹绝对路径，在本空间已经存放了官方提供的最近六个版本的so文件，包括`8.9.50` `8.9.58`或`8.9.63`，支持的所有版本号在txlib目录下，推荐使用高于8.9.50及以上的版本，也可以自行将so文件上传到空间的txlib文件夹中，选择自己的版本

版本号获取，登录一次go-cqhttp就能看见
<img width="502" alt="a5377513791a7fe990cf80c1c51e1506" src="https://github.com/alancu/qqsign/assets/136248463/8a0d61ee-f1a8-427f-bdb3-7bcc4d09de5c">

 
**ANDROID_ID：**

打开go-cqhttp→device.json

ctrl+f 搜索"android_id"

填写好后，点击**Duplicate this Space**，将自动部署

## 第三步：获取地址

当状态变成**Running**时，即部署成功

点击右上角三个点，选择**Embed this Space**

下方Direct URL就是你的接口地址，点**copy**复制到剪切板

## 第四步：填写并使用

打开config.yml

找到sign-server

此处填写为你复制的地址(URL)+/sign     

```plaintext
sign-server: 'URL/sign '
#注意 server:  此冒号右边需要加上一次空格
#也可复制我的格式，替换URL即可
```

### 如果最后还是登录不上可以尝试更换协议2，扫码登录

## 改写于CIkeyQi的go-cqhttp签名服务
<https://github.com/CikeyQi/QQsign_docs/blob/main/index.md>
