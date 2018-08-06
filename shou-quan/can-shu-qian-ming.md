# 参数签名

## 签名算法

 1 所有参数按参数名字母排序\(ASCII\)；  

 2排序后结果拼接成：参数名1=参数值1&参数名2=参数值2... &; 

 3 拼接玩后追加秘钥（秘钥联系福优网获取）; 

 4对拼接结果做md5。

注意：如果空参数建议不要向服务器发送，如果存在空参数向服务器发送，该参数需要签名。  


## 举例

```text
//参数
("trainDate","2018-07-09")
("fromStation","shanghai")
("toStation","beijing");
("timespan","1531122691");
签名秘钥：e10adc3949ba59abbe56e057f20f883e，此秘钥请联系福优网获取。
拼接后：fromStation=shanghai&timespan=1531122691&toStation=beijing&trainDate=2018-07-09&e10adc3949ba59abbe56e057f20f883e
签名结果：68F11EFFCD9974663DD46EF940F00319
使用：签名获取后，请在请求接口时，签名结果值填入sign参数。
```

## 示例代码\(JAVA\)

```text
/**
 * 签名demo
 * @param args
 */
public static  void main(String[] args){

    Map<String,String> srcparam = new HashMap<>();


    srcparam.put("appkey","88888888");
    srcparam.put("timespan",(new Date().getTime()/1000)+"");
   /* srcparam.put("toName","测试1");
    srcparam.put("bityName","株洲bB");
    srcparam.put("AityName","株洲bB");
    srcparam.put("timespan","1531103356");*/


    //将map.entrySet()转换成list
    List<Entry<String, String>> list =  new ArrayList<Entry<String, String>>(srcparam.entrySet());
    //转化成流排序、key转小写
    String paramString = list
            .stream()
            .filter(e -> !"sign".equals(e.getKey()))
            .sorted((o1, o2) -> o1.getKey().toLowerCase().compareTo(o2.getKey().toLowerCase()))
            .map(entry -> entry.getKey().toLowerCase() + "=" + entry.getValue() + "&")
            .collect(Collectors.joining(""));

    String appSecret = "d20adc3949ba59uzi56e057f20f684f"; //秘钥
    paramString = paramString.concat(appSecret);
    System.out.println(paramString);
    String signParam = DigestUtils.md5Hex(paramString).toUpperCase();
    log.info("签名为：" + signParam+",时间戳:"+srcparam.get("timespan"));
}
```

