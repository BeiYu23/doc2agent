# max.products

> 批量获取店铺商品信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.max.products` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/max/products` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2837 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_ids` | body | array | 否 | 商品id列表，手动配置要传，数量一次最多50个，智能配置不需要传 | `123,456` |
| `m_config_type` | body | mixed | 是 | 配置类型 0 手动配置，1 智能配置，默认手动配置 | `0` |
| `personalized_recommendation` | body | boolean | 否 | 个性化推荐(千人千面) | `false` |
| `auto_param` | body | object | 否 | 智能选品参数 | `` |
| `  └ display_num` | body | mixed | 否 | 展示数量 | `4` |
| `  └ order_type` | body | mixed | 是 | 选品类型, 排序方式, 0-销量排序，1-好评率排序，2-价格排序，3-上新时间排序 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/max/products?app_key=your_appkey_here&method=max.products&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status_code` | mixed | 状态码 | `0` |
| `status_msg` | string | 状态说明 | `success` |
| `data` | object | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 啊哦，服务器打瞌睡了，再试一次吧～（sub_code: isp.service-error:4） | 再试一次 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "products": [
        {
          "category_leaf_id": "20000",
          "check_status": "3",
          "name": "苹果手机",
          "original_price": "14",
          "pic": "https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933",
          "product_id": "123",
          "product_type": "1",
          "sale_price": "12",
          "sell_num": "99",
          "status": "0"
        }
      ]
    },
    "status_code": "0",
    "status_msg": "success"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:4",
  "sub_msg": "啊哦，服务器打瞌睡了，再试一次吧～"
}
```

## 备注
