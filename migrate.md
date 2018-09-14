步骤：<br><br>
1、把china_city表分割表lagou_city成字段为（id,province,city,ditrict），
表lagou_company 字段(cid, name, short_name, size, financestage)，表lagou_position字段 (pid, cityid, cid, position, field, salary_min, salary_max, workyear, education, ptype, pnature, advantage, published_at, updated_at)三个表。
<br><br>
2、china_city首先查询原表中所有的县，再查询市、省，根据条件字段parentId，id，再三表连接查询。
<br><br>
3、需要注意字段ditrict 有的数据为null ，所以还要插入语句追加到后面。
<br><br>
4、当china_city字段ditrict为空时，china_city和lagou_city，获取城市的id，前提是两个表中的字段ditrict一定为空，而表china_city中有的城市名后面不带有‘市’字，所以要使用（like）关键字。
<br><br>
5、china_city字段ditrict不为空时，获取id，查询china_city和lagou_city，根据他们的城市和县相同，使用union all 把步骤四跟步骤5查询出的结果创建新表插入表lagou_position。
<br><br>
6、lagou_position公司表还需要添加市id和ditrict。
<br><br>
7、从整理过的lagou_position，创建lagou_company公司表，分离出相关的字段，注意分离后从原备份表删除分离出去的字段。
<br><br>
8、自己还不能独立完成，感觉不会知道自己下一步要做什么。


