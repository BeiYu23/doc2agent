# shop.getStoreFreight

> 获取门店绑定的运费模版

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.getStoreFreight` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getStoreFreight` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2385 |
| 更新日期 | `2024-02-26` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/getStoreFreight?app_key=your_appkey_here&method=shop.getStoreFreight&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `store_freights` | array | 运费模版关联关系 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1:业务处理失败（sub_code: isv.business-failed:1） | 查看具体错误描述 |

## 响应示例

成功：

```json
{
  "data": {
    "store_freights": [
      {
        "freight_id": "123",
        "store_id": "123"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1",
  "sub_msg": "1:业务处理失败"
}
```

## 备注
