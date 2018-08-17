call_teacher **老师列表**

	id           编号
	name         姓名
	avatar       照片
	alias        称号
	desc         简介(基本简历+授课项目等介绍)
	call_num     已获得的call值
	sort         排序
	create_time  创建时间
	create_user  创建者
	update_time  修改时间
	update_user  修改者
	status       状态

call_student **用户列表**

	id           编号
	name         姓名
	phone        手机号
	call_num     剩余call值(可使用的call值)
	share_num    分享次数
	share_status 当日是否已分享(每天只能通过分享获得一次call值,00:00时更新所有用户的分享状态)
	create_time  创建时间
	update_time  修改时间
	update_user  修改者
	status       状态

call_log **打call记录表**

	id           编号
	stu_id       用户编号
	teacher_id   老师编号
	call_num     使用的call值
	create_time  创建时间


