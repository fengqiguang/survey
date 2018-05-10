# 问卷调查接口说明
测试域名：  http://127.0.0.1:8080/poly-survey-web/

## 项目工程接口列表

### 1 获取问卷接口 POST  /survey/getTemplateById
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
sendInfoId		|true    |int      |发送问卷id （从前端页面入口url参数获取，参数名为sendInfoId）

#### 响应参数类型说明
参数            |类型     |说明
---           |---      |---   
templateId    |int      |问卷模板id
templateName  |String   |问卷标题
hadAnswer 	  |int      |是否已答（0未答，1已答）
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
	"data": {
		"templateId": 1,
		"templateName": "消费观调查问卷",
		"hadAnswer": 0,
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
		},
		{
			"questionId": 3,
			"questionTitle": "对本次问卷有什么建议吗？",
			"questionType": 3,
			"options": [{
				"optionId": 6,
				"optionName": "",
				"sort": 1
			}]
		}
		]
}
```



### 2 提交问卷答案接口 POST  /survey/saveAnswer
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
openid      	|true     |String       |用户openid，从入口进来，参数名openid
sendInfoId      |true     |int          |发送问卷id （从前端页面入口url参数获取，参数名为sendInfoId）
answerJson      |true     |String       |答案json,格式：[{questionId:1,optionId:1,answerText:"xxxx"},{questionId:2,optionId:2,answerText:""}]，说明：questionId表示问题id，必填,optionId表示选项id,answerText为问答题填写的内容，多选的题目，有多个数据项。



#### 响应参数类型说明
参数            |类型     |说明
---             |---      |---
|无              | 无      |  无

#### 响应数据
成功或者失败


### 3 发送问卷模板消息 POST  /surveyWechat/sendSurveyTemplateMsg
#### 请求参数
参数            |必选     |类型     |说明
---             |---      |---      |---
wxConfigId      |true     |String       |微信wxConfigId
touserOpenid    |true     |String       |发送给的客户微信
sendInfoId      |true     |int          |问卷调查发送id



#### 响应参数类型说明
参数            |类型     |说明
---             |---      |---
|无              | 无      |  无

#### 响应数据
成功或者失败