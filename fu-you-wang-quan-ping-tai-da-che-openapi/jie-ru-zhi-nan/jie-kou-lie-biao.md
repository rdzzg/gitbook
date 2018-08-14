# 接口列表

## 接口列表查询

| 接口名称 | 请求地址 | 请求方式 | 接口说明 |
| :---: | :---: | :--- | :---: |
| 联想地址 | /allTaxi/address | GET |   |
| 能否用车 | /allTaxi/canUse | GET |   |
| 所有城市 | /allTaxi/cities | GET | 城市列表建议缓存至本地，每天刷星一次即可 |
| 获取城市服务车型 | /allTaxi/cityPrice | GET |   |
| 预估价 | /allTaxi/estimatePrice | GET |   |
| 坐标转城市ID | /allTaxi/getCityId | GET |   |
| 创建订单 | /allTaxi/order | POST | 预约单时间请传系统时间后半小时  |
| 订单详情 | /allTaxi/order/{orderNo} | GET |   |
| 取消订单 | /allTaxi/order/{orderNo}/cancel | PUT |   |
| 评分 | /allTaxi/order/{orderNo}/comment | PUT |   |
| 订单支付 | /allTaxi/order/{orderNo}/pay | PUT |   |
| 可用支付方式（H5使用） | /allTaxi/payType | GET |   |



