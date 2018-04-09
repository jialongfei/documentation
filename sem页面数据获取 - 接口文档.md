sem页面数据获取 - 接口文档

> 前缀可以是 xiaoying.net | www.xiao-ying.net | eggelite.com

> 统一返回数据格式:
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
    	xiaoying.net/sem_search?m=6&r=teacher
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


#### /sem_search_pcate

	功能:获取专业分类
	参数要求:无
	例:
		xiaoying.net/sem_search_pcate
	返回结果:
	{
	    "code": 200,
	    "status": true,
	    "msg": "",
	    "data": [
	        {
	            "id": "1",
	            "name": "商科",
	            "sort": "1",
	            "status": "0"
	        },
	        {
	            "id": "2",
	            "name": "理工科",
	            "sort": "2",
	            "status": "0"
	        },
	        {
	            "id": "3",
	            "name": "文科",
	            "sort": "3",
	            "status": "0"
	        },
	        {
	            "id": "4",
	            "name": "医药科",
	            "sort": "4",
	            "status": "0"
	        }
	    ]
	}

#### /sem_search_program

	功能:获取指定专业分类ID附属的所有专业详情
	参数要求:
		cate (必选 int) 专业分类ID
	例:
		xiaoying.net/sem_search_program?cate=1
	返回结果:
	{
	    "code": 200,
	    "status": true,
	    "msg": "",
	    "data": [
	        {
	            "id": "1",
	            "name": "金融统计学",
	            "content": "&lt;p&gt;&lt;span style=&quot;background-color: rgb(192, 80, 77);&quot;&gt;金融统计学&lt;/span&gt;&lt;/p&gt;",
	            "sort": "1",
	            "status": "1"
	        },
	        {
	            "id": "2",
	            "name": "物流管理学",
	            "content": "&lt;p&gt;&lt;span style=&quot;background-color: rgb(215, 227, 188);&quot;&gt;物流管理学&lt;/span&gt;&lt;/p&gt;",
	            "sort": "2",
	            "status": "1"
	        },
	        {
	            "id": "3",
	            "name": "市场营销经济学",
	            "content": "&lt;p&gt;&lt;span style=&quot;background-color: rgb(147, 137, 83);&quot;&gt;市场营销经济学&lt;/span&gt;&lt;/p&gt;",
	            "sort": "3",
	            "status": "1"
	        },
	        {
	            "id": "4",
	            "name": "旅游经济管理学",
	            "content": "&lt;p&gt;&lt;span style=&quot;background-color: rgb(253, 234, 218);&quot;&gt;旅游经济管理学&lt;/span&gt;&lt;/p&gt;",
	            "sort": "4",
	            "status": "1"
	        },
	        {
	            "id": "5",
	            "name": "国际贸易经济管理学",
	            "content": "&lt;p&gt;&lt;span style=&quot;background-color: rgb(178, 162, 199);&quot;&gt;国际贸易经济管理学&lt;/span&gt;&lt;/p&gt;",
	            "sort": "5",
	            "status": "1"
	        }
	    ]
	}

#### 错误示例

	请求接口:
		xiaoying.net/sem_search
	返回结果:
	{
	    "code": 200,
	    "status": false,
	    "msg": "缺少参数",
	    "data": []
	}