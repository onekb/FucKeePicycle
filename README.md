# FucKeePicycle(Fuck Keep Bicycle)

_仅供学习研究，请勿非法用途。_

## 原理
通过代理网络修改响应内容，达到本地客户端认为是会员目的。

## 代理以下URLs
```
https://api.gotokeep.com/*
```

## 相应内容做以下替换
```
# 左边为原内容 :冒号为分隔符 右边为替换内容
700014 : 0
"status":false : "status":true
```

## 如何使用
### 方式一：不用电脑 平板/手机 使用 [network_proxy_flutter](https://github.com/wanghongenpin/network_proxy_flutter/)
```
# 根据软件教程安装HTTPS代理
# 重写响应，添加URLs
https://api.gotokeep.com/*

# 左边为原内容 :冒号为分隔符 右边为替换内容
700014 : 0
"status":false : "status":true
```



### 方式二：电脑调试学习使用到的工具 [whistle](https://github.com/avwo/whistle) 
### 其他工具也可以，目的能替换就行了
参考方式一
