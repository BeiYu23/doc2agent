# second.alliance.mGetItems

> 【二方接口】根据推广id列表获取推广详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.alliance.mGetItems` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/7017 |
| 更新日期 | `2024-10-21` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `share_convert` | body | boolean | 否 | 是否转链 | `true` |
| `app_id` | body | mixed | 否 | 1 | `1` |
| `promotion_ids` | body | array | 否 | 推广id列表 | `1` |
| `author_id` | body | mixed | 否 | 作者id, 转链需要 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.alliance.mGetItems&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `promotions` | array | 推广列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "promotions": [
      {
        "item_type": "1",
        "product_id": "1",
        "promotion_id": "1",
        "title": "1"
      }
    ]
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
