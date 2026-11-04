# second.product.mGetAggs

> 【二方接口】获取评价信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.product.mGetAggs` |
| 中文名 | 【二方接口】获取评价信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/product/mGetAggs` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6930 |
| 更新日期 | `2024-10-10` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `gIds` | body | array | 否 | gIds | `[]` |
| `nDayAgo` | body | mixed | 否 | nDayAgo | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.product.mGetAggs&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 基础计数数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "key": "key",
        "value": {
          "appendsCount": "5883158",
          "badCount": "7444098",
          "badRatio": "7108218.0",
          "goodCount": "7727603",
          "goodRatio": "2533582.0",
          "newestCount": "3735100",
          "photoCount": "3719035",
          "total": "4431790"
        }
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
