---
description: 回调说明
---

# 回调

{% hint style="info" %}
1.  当订单状态发生改变时，福优网会通过回调服务将这些事件通知接入方。通知接入方需返回JSON格式的返回码“{‘rcode’:'0000'}”.若接入方回调失败，则会在一定时间内反复进行重试，若还是失败则消息丢弃
2.  当接入方收到回调后，需要重新调用订单详情接口，拉取最新的订单状态和信息，然后做相应处理
{% endhint %}

## 回调地址

下单时传入的回调地址

## 请求方式

POST

## 请求参数

| 参数名 | 类型 | 描述 | 必须 |
| :---: | :---: | :---: | :---: |
| orderNo | String | 订单号 | Y |
| orderNoApi | String | API订单号 | Y |
| flng | String | 出发地经度 | Y |
| flat | String | 出发地纬度 | Y |
| tlng | String | 目的地经度 | Y |
| tlat | String | 目的地纬度 | Y |
| stateName | String | 状态释义 | Y |
| estimatePrice | String | 预估价 | Y |
| source | String | 订单来源 | Y |
| from | String | 出发地 | Y |
| state | String | 状态 | Y |
| prices | String | 价格明细 | Y |
| outSourceNo | String | 服务商订单号 | Y |
| passengerName | String | 乘车人 | Y |
| passengerPhone | String | 乘车人电话 | Y |
| amount | String | 最终价格 | Y |
| level | String | 车型代码 | Y |
| toDetail | String | 目的地详细 | Y |
| totalAmount | String | 总价 | Y |
| insteadCall | String | 用车类型 | Y |
| to | String | 目的地 | Y |
| driverAvatar | String | 司机头像 | Y |
| driverCarType | String | 车辆品牌 | Y |
| driverOrderCount | String | 司机接单数 | Y |
| driverCard | String | 车牌 | Y |
| driverPhone | String | 司机电话 | Y |
| driverLevel | String | 司机等级 | Y |
| driverCarColor | String | 车辆颜色 | Y |
| driverName | String | 司机名 | Y |

