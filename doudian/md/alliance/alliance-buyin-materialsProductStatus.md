# buyin.materialsProductStatus

> 商品状态查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.materialsProductStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/materialsProductStatus` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1497 |
| 更新日期 | `2023-03-02` |

## 接口说明

- 文档书: 精选联盟API（版本 V5.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `products` | body | array | 是 | 商品 URL 列表，不超过50个 | `["https://haohuo.jinritemai.com/views/product/detail?id=798754293457134"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/materialsProductStatus?app_key=your_appkey_here&method=buyin.materialsProductStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "can_share": "true",
        "join_alliance": "true",
        "product_url": "https://haohuo.jinritemai.com/views/product/detail?id=798754293457134",
        "promotion_status": "2",
        "status": "0"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
