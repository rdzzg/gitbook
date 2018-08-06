# 接口列表

接口标准请参考swagge火车票业务

| 接口名称 | 请求地址 | 请求方式 | 接口说明 |
| :--- | :--- | :--- | :--- |
| 查询所有车站 | /train/stations | GET  |  |
| 车次查询接口 | /train/shifts/{fromStation}/{toStation}/{trainDate} | GET |  |
| 经停站查询 | /train/stopStations/{trainNo}/{fromStation}/{toStation}/{trainDate} | GET |  |
| 单车次查询 | /train/train/{trainNo}/{trainDate} | GET |  |
| 余票查询 | /train/tickets | GET |  |
| 创建订单 | /train/order | POST | 占座 |
| 付款出票 | /order/pay/1017 | POST |  |
| 取消订单 | /train/order/cancel | PUT |  |
| 申请退票 | /train/order/refund | PUT |  |
| 订单详情 | /train/order/{orderNo} | GET |  |



