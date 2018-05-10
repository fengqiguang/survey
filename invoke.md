# 调用调查问卷启动发送任务
域名：  poly-survey-web/invoke/invoke


### 1 调用启动发送调查问卷任务接口 POST  /invoke/invoke
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
customerType    |true     |int      |客户类型（1 扫码客户  2 建档客户  3 成交客户）
memberInfoId    |true     |int      |会员id
buildingId      |true     |int      |楼盘id
sellId          |fasle    |int      |置业顾问id（当前客户有归属顾问就需要传）
wxconfigid      |true     |string   |微信wxconfigid
businessId      |fasle    |int      |业务id（）

#### 响应参数类型说明
参数            |类型     |说明
---             |---      |---
无                | 无        |  无

#### 响应数据
成功或者失败
