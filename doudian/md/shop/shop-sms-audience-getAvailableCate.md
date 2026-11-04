# sms.audience.getAvailableCate

> 获取商家类目id

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.sms.audience.getAvailableCate` |
| 中文名 | 获取商家类目id |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/audience/getAvailableCate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/7662 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `token` | body | string | 否 | 组件mcToken，参考api：https://op.jinritemai.com/docs/api-docs/162/3586 | `组件token` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sms.audience.getAvailableCate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `category_list` | array | 类目列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "category_list": [
      {
        "category_id": "210001",
        "category_name": "美妆",
        "child_category": [
          {
            "category_id": "210001",
            "category_name": "美妆",
            "child_category": [
              {
                "category_id": "220001",
                "category_name": "三级类目名称",
                "level": "3"
              }
            ],
            "level": "2"
          }
        ],
        "level": "1"
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
