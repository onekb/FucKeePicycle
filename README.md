# FucKeePicycle(Fuck Keep Bicycle)

_仅供学习研究，请勿非法用途。_

## 原理
通过代理网络修改响应内容，达到本地客户端认为是会员目的。

## 代理以下URLs
```
^https://kit.gotokeep.com/puncheur/v3/shadow/routes/*/detail$
^https://api.gotokeep.com/nuocha/course/v2/*/preview*
^https://api.gotokeep.com/nuocha/plans/*/start*
^https://kit.gotokeep.com/gerudo/v2/liveStream/config/*
^https://kit.gotokeep.com/gerudo/v1/liveCourse/*/details
https://api.gotokeep.com/kprime/v2/auth
```

## 相应内容做以下替换
```
# 左边为原内容 :冒号为分隔符 右边为替换内容
"userMemberStatus":false : "userMemberStatus":true
"userLiveMemberStatus":false : "userLiveMemberStatus":true
"userIdentityType":5 : "userIdentityType":1
"willExpireDays":0 : "willExpireDays":3660
"canWatchLive":false : "canWatchLive":true
"userLiveMemberExpireTime":0 : "userLiveMemberExpireTime":1776630399000
"normalMember":false : "normalMember":true
"liveMember":false : "liveMember":true
"hasLiveMembership":false : "hasLiveMembership":true
"hasPaid":false : "hasPaid":true
"canPractiseScreenshotAndRecording":false : "canPractiseScreenshotAndRecording":true
"status":false : "status":true
"memberStatus":"never" : "memberStatus":"member"
"status":3 : "status":1
"statusTrack":"expired" : "statusTrack":"valid"
```

## 如何使用
### 方式一：不用电脑 平板/手机 使用 [network_proxy_flutter](https://github.com/wanghongenpin/network_proxy_flutter/)
```
# 根据软件教程安装HTTPS代理
# 请求重写，添加URLs
https://kit.gotokeep.com/*
https://api.gotokeep.com/*

# 修改响应 添加这15条 （上面两个链接都把这些替换写进去）
# 左边为原内容 :冒号为分隔符 右边为替换内容
"userMemberStatus":false : "userMemberStatus":true
"userLiveMemberStatus":false : "userLiveMemberStatus":true
"userIdentityType":5 : "userIdentityType":1
"willExpireDays":0 : "willExpireDays":3660
"canWatchLive":false : "canWatchLive":true
"userLiveMemberExpireTime":0 : "userLiveMemberExpireTime":1776630399000
"normalMember":false : "normalMember":true
"liveMember":false : "liveMember":true
"hasLiveMembership":false : "hasLiveMembership":true
"hasPaid":false : "hasPaid":true
"canPractiseScreenshotAndRecording":false : "canPractiseScreenshotAndRecording":true
"status":false : "status":true
"memberStatus":"never" : "memberStatus":"member"
"status":3 : "status":1
"statusTrack":"expired" : "statusTrack":"valid"
```



### 方式二：电脑调试学习使用到的工具 [whistle](https://github.com/avwo/whistle) 
### 其他工具也可以，目的能替换就行了
```
Rules 规则
https://comb-platform.hortorgames.com/comb-custom-switch-server/api/v1/switch/multi/status file://{comb}
line`
^https://kit.gotokeep.com/puncheur/v3/shadow/routes/*/detail$
resReplace://{test.json}
`

line`
^https://api.gotokeep.com/nuocha/course/v2/*/preview*
resReplace://{test.json}
`

line`
^https://api.gotokeep.com/nuocha/plans/*/start*
resReplace://{test.json}
`

line`
^https://kit.gotokeep.com/gerudo/v2/liveStream/config/*
resReplace://{test.json}
`

line`
^https://kit.gotokeep.com/gerudo/v1/liveCourse/*/details
resReplace://{test.json}
`

line`
https://api.gotokeep.com/kprime/v2/auth
resReplace://{test.json}
`
```

```
Values test.json

"userMemberStatus":false : "userMemberStatus":true
"userLiveMemberStatus":false : "userLiveMemberStatus":true
"userIdentityType":5 : "userIdentityType":1
"willExpireDays":0 : "willExpireDays":3660
"canWatchLive":false : "canWatchLive":true
"userLiveMemberExpireTime":0 : "userLiveMemberExpireTime":1776630399000
"normalMember":false : "normalMember":true
"liveMember":false : "liveMember":true
"hasLiveMembership":false : "hasLiveMembership":true
"hasPaid":false : "hasPaid":true
"canPractiseScreenshotAndRecording":false : "canPractiseScreenshotAndRecording":true
"status":false : "status":true
"memberStatus":"never" : "memberStatus":"member"
"status":3 : "status":1
"statusTrack":"expired" : "statusTrack":"valid"
```
