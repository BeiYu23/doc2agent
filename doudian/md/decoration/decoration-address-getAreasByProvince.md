# address.getAreasByProvince

> 查询最新的四级地址用于订单售后处理

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.address.getAreasByProvince` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/getAreasByProvince` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/1844 |
| 更新日期 | `2022-08-08` |

## 接口说明

- 文档书: 店铺装修API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `province_id` | body | number | 是 | 省ID | `41` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/getAreasByProvince?app_key=your_appkey_here&method=address.getAreasByProvince&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 响应结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 422:provId invalid（sub_code: isv.business-failed:422） | 参数传入有问题，请检查后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "code": "41",
        "father_code": "8",
        "level": "Province",
        "name": "河南省",
        "sub_districts": [
          {
            "code": "410500",
            "father_code": "41",
            "level": "City",
            "name": "安阳市",
            "sub_districts": [
              {
                "code": "410522",
                "father_code": "410500",
                "level": "District",
                "name": "安阳县",
                "sub_districts": [
                  {
                    "code": "410522107",
                    "father_code": "410522",
                    "level": "Street",
                    "name": "伦掌镇"
                  }
                ]
              }
            ]
          }
        ]
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
  "sub_code": "isv.business-failed:422",
  "sub_msg": "422:provId invalid"
}
```

## 备注
