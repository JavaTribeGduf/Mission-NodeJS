# 基于 mongoDB 的用户登录

你以为结束了吗？这个任务才是最终 Boss，将你所学的知识融会贯通，击败它吧

要求：

1. 安装 mongoDB 数据库，建立两个 collection:
   1. collection: user, 字段 name, salt, password
   1. collection: number, 字段 userid, number
1. 实现以下 API:
   1. /login, 参数: name, password, 功能: 判断用户名密码是否匹配，是的话把{userid:user.\_id}放到 session 并返回字符串`Hello ${name}`
   1. /start, 拦截未登录用户，生成一个随机数，存放到 number 表
   1. /:number, 拦截未登录用户, 功能: session 中获取 userid, 数据库查出该用户 number 表中的值，跟参数进行对比， 返回 big/small/equal
1. 为每个 API 编写至少一个测试用例，要求测试代码执行完后，数据库不能残留测试数据

参考实现时间：16 小时
