# 获取可图片鉴定的品牌

> btas.listBrand — 获取可图片鉴定的品牌

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取可图片鉴定的品牌 |
| 文档地址 | `/docs/doudian/btas-inspect/btas-inspect-btas-listBrand` |
| 接口 ID | `doudian.btas-inspect.btas.listBrand` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/btas/listBrand` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/49/1865 |
| 更新日期 | `2021-06-07` |

## 接口说明

- 文档书: BTAS质检API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/btas/listBrand?app_key=your_appkey_here&method=btas.listBrand&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brand_list` | array | 品牌列表 | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "brand_list": [
      {
        "brand_category_list": [
          {
            "id": "1",
            "name": "鞋靴"
          }
        ],
        "brand_id": "1",
        "brand_name": "\"aj\""
      }
    ]
  },
  "err_no": 0,
  "message": "success",
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
