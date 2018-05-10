# 微信用户相关接口说明
测试域名：  http://moss.canplay.com.cn/moss/customer


### 1 发送短信验证码接口 POST  /wx/sendMobileValidCode
#### 请求参数
参数            |必选      |类型     |说明
---             |---      |---      |---
mobile          |true     |String   |接收者手机号


#### 响应参数类型说明
参数        	|类型    	|说明
---         	|---    	|---
                |         	|  

#### 响应数据
成功或失败



### 2 账户（手机号）绑定接口 POST  /wx/wxBindPhone
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
mobile          |true     |String   |绑定手机号
mobileCode      |true     |double   |验证码

#### 响应参数类型说明
参数        	|类型    	|说明
---         	|---    	|---
                |         	|  

#### 响应数据
成功或失败



### 3 查询个人信息接口 POST  /wx/getUserInfo
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
无              |         |         |  

#### 响应参数类型说明
参数        	|类型    	|说明
---         	|---    	|---
userId        |long     |用户id
nickname      |string   |姓名
resourceKey   |string   |头像地址    
mobile        |string   |电话  
address       |string  |地址
integral      |int    |积分

#### 响应数据
```json
"data":{
	"userId":10,
	"nickname":"测试用户",
	"resourceKey":"1",
	"mobile":"10086",
	"address":"深圳xxx"，
	"integral":0
}
```


### 4 更新用户个人信息 POST  /wx/updateUserInfo
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
nickname        |true     |String   |姓名
mobile          |true     |String   |电话  
address         |false    |String   |地址

#### 响应参数类型说明
参数        	|类型    	|说明
---         	|---    	|---
                |         	|  

#### 响应数据
成功或失败