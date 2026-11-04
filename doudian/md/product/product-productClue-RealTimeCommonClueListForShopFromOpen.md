# productClue.RealTimeCommonClueListForShopFromOpen

> 商机推荐接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.productClue.RealTimeCommonClueListForShopFromOpen` |
| 中文名 | 商机推荐 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/productClue/RealTimeCommonClueListForShopFromOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7743 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_type_new` | body | mixed | 否 | 新版线索类型-商机首页改版 | `11` |
| `terminal_type` | body | mixed | 否 | 端类型，区分source是业务类型 | `2` |
| `shop_source` | body | string | 否 | SDK布点来源 | `zndz_supply_distribution` |
| `condition` | body | object | 否 | 查询条件 | `` |
| `  └ price_highest` | body | mixed | 否 | 价格上限，单位分 | `2400` |
| `  └ rights_id_list` | body | array | 否 | 权益id列表，且条件 | `[1]` |
| `  └ clue_brand_exist` | body | boolean | 否 | 是否知名品牌 | `false` |
| `  └ zndz_supply_product_guarantee_ids` | body | array | 否 | 智能店长货源保障id列表 | `[1,2]` |
| `  └ clue_id_list` | body | array | 否 | 商机id了列表 | `[1,2]` |
| `  └ task_id_list` | body | array | 否 | 招募任务列表 | `[1]` |
| `  └ brand_ids` | body | array | 否 | 品牌ID | `[1,2,3]` |
| `  └ content_types` | body | array | 否 | 优势体裁类型，仅支持video/live/product_card | `["video"]` |
| `  └ tag_id_list` | body | array | 否 | 标签id列表，且条件 | `[1,2,3,4]` |
| `  └ online_time_type` | body | string | 否 | 上新时间类型，仅支持1d/7d/30d | `1d` |
| `  └ only_show_zndz_supply_exists` | body | boolean | 否 | 是否获取包含智能店长货源的商机 | `false` |
| `  └ sort` | body | object | 否 | 排序字段，SortField = 匹配程度(MATCH_DEGREE),成交规模(TRANSACTION_SIZE),搜索热度(SEARCH_POPULARITY),缺货程度(OUT_OF_STOCK_LEVEL) | `` |
| `    └ need_sort` | body | boolean | 否 | 是否需要排序 | `true` |
| `    └ direction` | body | mixed | 否 | 升序或者降序 | `1` |
| `    └ sort_field` | body | string | 否 | 排序字段 | `HEAT_OF_DEMAND` |
| `  └ clue_info` | body | string | 否 | 线索关键字 | `女装` |
| `  └ categories` | body | array | 否 | 类目筛选 | `` |
| `    └ first_cid` | body | mixed | 否 | 1级类目id | `20004` |
| `    └ leaf_cid` | body | mixed | 否 | 叶子类目ID | `5` |
| `    └ fourth_cid` | body | mixed | 否 | 4级类目id | `4` |
| `    └ third_cid` | body | mixed | 否 | 3级类目id | `3` |
| `    └ second_cid` | body | mixed | 否 | 2级类目id | `2` |
| `  └ price_lowest` | body | mixed | 否 | 价格下限，单位分 | `1200` |
| `  └ biz_topic_i_ds` | body | array | 否 | 主题id列表 | `[1]` |
| `page` | body | object | 否 | 分页参数 | `` |
| `  └ current` | body | mixed | 否 | 当前页 | `1` |
| `  └ offset` | body | mixed | 否 | 起点，适用每页大小不同的场景，无需前端重新适配计算分页信息 | `1` |
| `  └ page_size` | body | mixed | 否 | 每页数量 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/productClue/RealTimeCommonClueListForShopFromOpen?app_key=your_appkey_here&method=productClue.RealTimeCommonClueListForShopFromOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `200` |
| `data` | array | 线索列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 500:RealTimeCommonClueListForShopFromOpen clueList query err（sub_code: isv.business-failed:500） | 请联系API负责人 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "clue_detail": {
          "clue_channel": "industry_selected",
          "clue_id": "47142433",
          "clue_label_list": [
            {
              "label_desc": "近7日全网热卖",
              "label_id": "35",
              "label_name": "近7日全网热卖"
            }
          ],
          "name": "高像素中画幅相机",
          "product_pic_url": "https://p3-dy-ecom-biz-chance.byteimg.com/tos-cn-i-267oifhqau/293b93f7c9da4f5ebb3a8c1de83f9516",
          "profit_tags": [
            {
              "profit_id": "3",
              "profit_name": "上新扶持"
            }
          ]
        },
        "clue_indicator": {
          "pay_amt_rate": "1.23",
          "search_pv_cnt_range": "5万-10万"
        },
        "zndz_supply_info": {}
      }
    ],
    "total": "200"
  },
  "code": 10000,
  "msg": "success",
  "sub_code": "",
  "sub_msg": ""
}
```

失败：

```json
{
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:500",
  "sub_msg": "500:RealTimeCommonClueListForShopFromOpen clueList query err"
}
```

## 备注
