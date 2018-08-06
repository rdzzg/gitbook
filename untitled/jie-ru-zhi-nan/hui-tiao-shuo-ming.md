# 回调说明

## 火车票结果通知回调

火车票业务中，涉及到占座、出票、退票、改签、超时订单等状态变更后API会主动推送相关状态。

## 回调参数

| 参数名 | 参数类型 | 是否必填 | 参数说明 |
| :--- | :--- | :--- | :--- |
| rcode  | string | 是 | 返回码  |
| desc  | string | 否 | 消息文本 |
| method  | string | 是 | 通知类型  |
| orderNo  | string | 否 | 订单号 |
| data | string | 否 | 详细信息具体参考如下案例 |

## 占座回调推送案例

```text
orderNo=20180711134121178003,
method=seat,
data={
   "departureTime":1532900880000,
   "passengers":[
	{
           "passengerName":"张三",
           "serviceCharge":0,
           "passengerType":1,
           "price":59.5,            
           "seatClass":"3",            
           "cardType":"1",            
           "pTicketNo":"E150887738101005F",            
           "passengerId":"8693001",            
           "seatNo":"01车厢,05F号",            
           "cardNo":"36072119940603xxxx",            
           "insuranceCharge":0        
     }
   ],
   "toStationCode":"226",    
   "trainNo":"G7072",    
   "fromStation":"上海",    
   "isSelfToProxy":false,    
   "toStation":"苏州",    
   "originalOrderNo":"",    
   "isChangedOrder":0,    
   "orderAmount":59.5,    
   "ticketNo":"E150887738",   
   "arrivalTime":1532902500000,    
   "expirationTime":1531302183000,    
   "fromStationCode":"321",    
   "orderNoSupplier":"TFT5B45CB412012969U2F1998" 
 }, 
 rcode=000000, 
 desc=占座成功  

```

## 出票结果推送参数案例

```text
orderNo=20180712134121178010, 
method=ticket, 
data={
    "ticketGate":"候车地点：候车室7",
    "orderNoSupplier":"TFT5B470AB50012CFAU391998",
    "issueTime":"2018-07-12 16:01:26"
},
rcode=000000, 
desc=出票成功
```

## 订单过期推送参数案例（调了取消订单后或者占座后25分钟未付款）

```text
orderNo=20180711134121178003,
method=overTime,
data={
    "orderNoSupplier":"TFT5B45BF60101293C2291998"
},
rcode=170207,
desc=订单已过期
订单取消参数：
params:
orderNo=20180711134121178003,
method=cancel,
data={
    "orderNoSupplier":"TFT5B47098C0012CF682A1998",
    "cancelTime":"2018-07-12 15:57:00"
},
rcode=000000,
desc=取消成功
```

## 取消结果推送案例推送

```text
orderNo=20180711134121178003,
method=cancel,
data={
    "orderNoSupplier":"TFT5B47098C0012CF682A1998",
    "cancelTime":"2018-07-12 15:57:00"
},
rcode=000000,
desc=取消成功
```

## 退票结果推送：（调了退票接口）

```text
orderNo=20180712134121178010,
method=refund,
data={
    "orderNoSupplier":"TFT5B470AB50012CFAU391998",
    "refundTime":"2018-07-12 16:23:43",
    "refundPrice":"59.50",
    "refundType":"online",
    "passengers":[
        {
            "passengerId":"8696108",
            "pTicketNo":"E021806438101005D",
            "passengerName":"张三",
            "passengerType":"1",
            "cardType":"1",
            "cardNo":"36072119940603xxxx",
            "refundPrice":"59.50"
        }
    ]
},
rcode=000000,
desc=线上退票成功
```

