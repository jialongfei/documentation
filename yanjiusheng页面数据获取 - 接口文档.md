sem页面数据获取 - 接口文档

> 返回数据格式:
{
	code:200 ,	# 请求成功
	status:bool,# true=正常 | false=异常
	msg:'',		# status为false时会有错误提示信息
	data:[]		# 返回数据,status为false时data为[]
}

#### /sem_search

	功能:获取和主分类表有关联的数据,如: 
		老师(teacher),专业(program),学校(school)...
	参数要求:
		m (必选 int) 主分类ID
        r (必选 string) 查询范围(表名)
    例:
    	test.com/sem_search?m=6&r=teacher
    返回结果:
    {
	    "code": 200,
	    "status": true,
	    "msg": "",
	    "data": [
	        {
	            "id": "1",
	            "name": "张三丰",
	            "avatar": "/Resources/sem/teacher/2018-04-09/5acac678b1e10.jpg",
	            "from": "东京大学",
	            "job": "金牌顾问",
	            "desc": "成功帮助666名学生进入名校",
	            "sort": "2",
	            "status": "1"
	        },
	        {
	            "id": "2",
	            "name": "周芷若",
	            "avatar": "/Resources/sem/teacher/2018-04-09/5acac6ee1736c.jpg",
	            "from": "帝景大学",
	            "job": "教务长",
	            "desc": "资深教务老师,好评率100%.",
	            "sort": "1",
	            "status": "1"
	        }
	    ]
	}

#### 错误示例

	请求接口:
		test.com/sem_search
	返回结果:
	{
	    "code": 200,
	    "status": false,
	    "msg": "缺少参数",
	    "data": []
	}