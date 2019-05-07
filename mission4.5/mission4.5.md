# 单元测试

完成前四个任务其实已经掌握 Node.js 的基本用法，并且简单体验了没有 Ajax 的前后端合作。接下来要引进一个新概念：测试

JS 测试工具分测试框架和断言库两类：

- 常见测试框架: mocha, jest, jasmine
- 常见断言库: should, expect, chai

练习：使用 mocha+shouldjs，对猜数字游戏 API 进行单元测试，包含三个测试单元：

1. 对 /start 接口的测试，断言回复 OK
1. 对 /:number 接口的测试，断言回复 bing 或 small 或 equal

参考实现时间：4 小时
