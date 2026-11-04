# buyin.getDeliveryActivityProds

> 三方获取活动页商品货池

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.getDeliveryActivityProds` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/getDeliveryActivityProds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/7460 |
| 更新日期 | `2025-06-25` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | array | 否 | 上限为1 | `[]` |
| `page` | body | mixed | 否 | 1开始 | `1` |
| `size` | body | mixed | 否 | 上限1000 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/getDeliveryActivityProds?app_key=your_appkey_here&method=buyin.getDeliveryActivityProds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 商品id总数 | `0` |
| `prod_id` | array | 商品id列表 | `[]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "prod_id": "[]",
    "total": "0"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
