# 问卷调查接口说明
测试域名：  http://127.0.0.1/poly-survey-web/

## 项目工程统一返回参数模板
	
	本项目统一返回格式含code（相应状态码0表示成功,其他参考错误码对应列表文档）、msg（错误信息）、times（时间戳）、data（返回内容）

	例如：

	{
	"code": 0,
	"msg": "",
	"times": 1525404202761,
	"data": "{memberName:'zhangsan',openid}"
	}



### 1 获取问卷接口 POST  /survey/getSurveyTemplate
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
templateId      |true     |id       |问卷模板id


#### 响应参数类型说明
参数            |类型     |说明
---           |---      |---   
code    	  |int      |相应状态码（0表示成功）
msg  		  |String   |错误信息
times 		  |int      |时间戳
data 		  |Object   |返回内容
templateId    |int      |问卷模板id
templateName  |String   |问卷标题
questionCount |int      |问卷答题个数
firstLanguage |String   |问卷首语
lastLanguage  |String   |问卷尾语
questions     |Array    |问题集合
  questionId    |int      |问题id
  questionTitle |String   |问题标题
  questionType  |int      |问题类型（1单选 2 多选 3 问题）
   options     |Array    |选项集合
   optionId    |int      |选项id
   optionName  |String   |选项名称
   sort        |排序      |选项排序

#### 响应数据
```json
{
	"code": 0,
	"msg": "",
	"times": 1525404202761,
	"data": {
		"templateId": 1,
		"templateName": "消费观调查问卷",
		"questionCount": 2,
		"firstLanguage": "您好，我们是XXX，我们正在进行一项关于消费观的调查，想邀请您用几分钟时间帮忙填答这份问卷。本问卷实行匿名制，所有数据只用于统计分析， 请您放心填写。题目选项无对错之分，请您按自己的实际情况填写。谢谢您的帮助。",
		"questions": [{
			"questionId": 1,
			"questionTitle": "你的性别？",
			"questionType": 1,
			"options": [{
				"optionId": 1,
				"optionName": "男",
				"sort": 1
			}, {
				"optionId": 2,
				"optionName": "女",
				"sort": 2
			}]
		}, {
			"questionId": 2,
			"questionTitle": "你一般每个月花费主要在哪些方面？",
			"questionType": 1,
			"options": [{
				"optionId": 3,
				"optionName": "伙食",
				"sort": 1
			}, {
				"optionId": 4,
				"optionName": "学习",
				"sort": 2
			}, {
				"optionId": 5,
				"optionName": "娱乐",
				"sort": 3
			}]
		}]
	}
}
```



### 2 提交问卷答案接口 POST  /survey/saveAnswer
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
openid      	|true     |String       |问卷模板id
sendInfoId      |true     |int          |发送问卷id 
answerJson      |true     |String       |答案json,格式：[{questionId:1,optionId:1,answerText:"xxxx"},{questionId:2,optionId:2,answerText:""}]


#### 响应参数类型说明
参数            |类型     |说明
---           |---      |---   
code    	  |int      |相应状态码（0表示成功）
msg  		  |String   |错误信息
times 		  |int      |时间戳
data 		  |Object   |返回内容

#### 响应数据

```json
{
	"code": 0,
	"msg": "",
	"times": 1525404202761,
	"data": ""
}
```

