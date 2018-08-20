# 打call接口文档

---

#### 读取老师列表

	路由: xy/call/teacher
	所需参数:
		无
	返回数据:
	成功:
		{
		    "status": true,
		    "data": [
		        {
		            "id": "4",
		            "name": "* 老师姓名",
		            "alias": "老师称号",
		            "avatar": "./Uploads/koubei/2018-08-16/5b750b5719433.png",
		            "desc": "老师简介\n",
		            "vd_code": "视屏嵌入代码",
		            "vd_desc": "视频简介\n",
		            "good": "./Uploads/koubei/2018-08-16/5b750b51066b1.png",
		            "call_num": "666",
		            "outer": "暂未获得关注~"
		        },
		        {
		        	more...
		        }
		    ]
		}
		字段说明
		// id = 老师编号
		// name = 老师姓名
		// alias = 老师称号
		// avatar = 老师照片
		// desc = 老师简介
		// vd_code = 视频嵌入代码
		// vd_desc = 视频简介
		// good = 学员好评截图
		// call_num = 获得call值
		// outer = 无用字段
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}


#### 登录/注册前获取短信验证码:

	路由: xy/call/sendsms
	所需参数:
		phone  必须 手机号码
	返回数据:
	成功:
		{
		    "status": true
		}
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}

#### 用户提交注册/登录

	路由: xy/call/stu/create
	所需参数:
		name   必须 用户姓名
		phone  必须 手机号码
		code   必须 短信验证码
	返回数据:
	成功:
		{
		    "status": true,
		    "res": {
		        "name": "张三",
		        "phone": "15988805856",
		        "code": "7238",
		        "call_num": 5,
		        "share_num": 0,
		        "share_status": 0,
		        "create_time": 1534413270,
		        "status": 1,
		        "id": "13"
		    }
		}
		字段说明
		// name = 姓名
		// phone = 手机号码
		// code = 验证码
		// call_num = 剩余call值
		// share_num = 分享次数
		// share_status = 分享状态
		// create_time = 创建时间
		// status = 学员状态 1=正常 0=异常
		// id = 用户编号
	注意: 这里返回的数据需要保存在客户端,以便用户发起打call或分享请求的时候传递用户信息
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}

#### 创建打call记录

	路由: xy/call/create
	所需参数:
		ui   必须 用户编号
		ti   必须 老师编号
		p    必须 用户手机号码
		c    必须 打call数量
	返回数据:
	成功:
		{
		    "status": true,
		    "msg": "打call成功!"
		}
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}

#### 分享获取call值

	路由: xy/call/share
	所需参数:
		ui   必须 用户编号
	返回数据:
	成功:
		{
		    "status": true,
		    "msg": "分享成功,10个Call值已进入您的账户!"
		}
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}


#### 学员打call排行榜

	路由: xy/call/student
	所需参数:
		无
	返回数据:
	成功:
		{
		    "status": true,
		    "data": [
		        {
		            "id": "4",
		            "name": "dragon2",
		            "call_num": "0",
		            "share_num": "6",
		            "outer": "共获得 65 个call值,近期为 4 位老师打call 31 次,共使用 65 个call值"
		        },
		        {
		            more...
		        }
		    ]
		}
		字段说明
		// id = 学员编号
		// name = 学员姓名
		// call_num = 剩余call值
		// share_num = 分享次数 (分享过几次)
		// outer = 无用信息
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}

#### 读取所有打call记录	

	路由: xy/call/log
	所需参数:
		无
	返回数据:
	成功:
		{
		    "status": true,
		    "data": [
		        {
		            "stu_id": "4",
		            "tea_id": "1",
		            "call_num": "1",
		            "create_time": "07-31 15:11:20",
		            "student": "dragon2",
		            "teacher": "张老师",
		            "title": "07-31 15:11:20 | dragon2 为 张老师 打call x 1"
		        },
		        {
		            more...
		        }
		    ]
		}
		字段说明
		// stu_id = 学员编号
		// tea_id = 老师编号
		// call_num = 打call数 (本次记录打了几个call)
		// create_time = 打call时间
		// student = 学员姓名
		// teacher = 老师姓名
		// title = 无用信息
	失败:
		{
		    "status": false,
		    "msg": "错误信息"
		}