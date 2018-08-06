---
description: 电影票接口列表
---

# 接口列表

## 接口列表查询

| 接口名称 | 请求地址 | 请求方式 | 接口说明 |
| :---: | :---: | :---: | :---: |
| 即将上映电影 | /film/films/coming\_soon | GET |   |
| 所有城市 | /film/cities | GET | 建议数据缓存到本地，一天更新一次 |
| 电影列表 | /film/films/{cityName} | GET |   |
| 电影上映日期 | /film/dates/{cityName}/{filmId} | GET |   |
| 影院上映电影 | /film/films/in\_theaters/{cinemaId} | GET |   |
| 正在上映某部电影的影院列表 | /film/cinemas | GET |   |
| 区域城市 | /film/regions/{cityName} | GET |   |
| 上映场次列表 | /film/shows/{cinemaId}/{showDate}/{filmId} | GET |   |
| 影厅座位信息 | /film/seats/{cinemaId}/{hallId}/{showId} | GET |   |
| 场次详情 | /film/show/{showId} | GET |   |
| 已售出座位 | /film/usedseats/{showId} | GET |   |
| 下单接口 | /film/order | POST |   |
| 付款出票 | /order/pay/1009 | POST |   |
| 查询订单 | /film/order/{orderNo} | GET |   |
| 取消订单 | /film/order/cancle/{orderNo} | DELETE |   |

