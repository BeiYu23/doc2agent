# shopVideo.searchItem

> 查询视频列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.searchItem` |
| 中文名 | 查询视频列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/searchItem` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7486 |
| 更新日期 | `2025-06-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 否 | 页码 | `1` |
| `bind_scene` | body | mixed | 否 | 绑定场景，1-只查挂车短视频，2-查询所有非挂车短视频，3-查询所有未绑定商品的短视频 | `1` |
| `optional_param` | body | object | 否 | 可选参数: 是否获取相关数据 | `` |
| `  └ need_stats` | body | boolean | 否 | 是否需要短视频表现 | `false` |
| `  └ need_high_quality_tag` | body | boolean | 否 | 是否需要优质标签 | `false` |
| `page_size` | body | mixed | 否 | 每页数量，默认10 | `10` |
| `user_id` | body | string | 否 | 作者账号id，不传默认人店一体账号，支持渠道号 | `121212` |
| `item_id` | body | string | 否 | 短视频id | `121221221` |
| `product` | body | object | 否 | 商品参数 | `` |
| `  └ product_id` | body | string | 否 | 商品id | `1212121212` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/searchItem?app_key=your_appkey_here&method=shopVideo.searchItem&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |
| `total` | mixed | 总数 | `121212` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1000001:当前商家暂未绑号（sub_code: isv.business-failed:1000001） | 请商家绑号 |
| `50002` | 业务处理失败 / 20000000:下游服务内部异常(code=20000004)（sub_code: isv.business-failed:20000000） | 稍后重试 |
| `50002` | 业务处理失败 / 1000003:系统异常（sub_code: isv.business-failed:1000003） | 系统异常 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "items": [
        {
          "account_info": {
            "name": "这是名称",
            "user_id": "1212121"
          },
          "bind_types": "[1]",
          "high_quality_tag": {
            "boost_v_v": "1212",
            "high_quality": "true"
          },
          "item_info": {
            "caption": "这是描述",
            "cover": "https://ttt",
            "duration": "11",
            "item_id": "12121221",
            "name": "这是标题",
            "publish_time": "1748347421",
            "reviewed": "true",
            "status": "102"
          },
          "products": {
            "bind_products": [
              {
                "bind_type": "1",
                "products": [
                  {
                    "id": "12121212",
                    "img": "https://ttt",
                    "name": "这是商品名称"
                  }
                ]
              }
            ],
            "suggest_products": [
              {
                "id": "121212121",
                "img": "https://www.",
                "name": "这是产品名称"
              }
            ]
          },
          "shop_info": {
            "shop_id": "4463798"
          },
          "stats": {
            "comment_count": "12121",
            "like_count": "1212",
            "order_amount": "1234",
            "play_count": "1223",
            "share_count": "1221"
          }
        }
      ]
    },
    "total": "121212"
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
  "sub_code": "isv.business-failed:1000001",
  "sub_msg": "1000001:当前商家暂未绑号"
}
```

## 备注
