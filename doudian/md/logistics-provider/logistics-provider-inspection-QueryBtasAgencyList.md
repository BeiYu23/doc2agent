# inspection.QueryBtasAgencyList

> 查询btas质检机构列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.inspection.QueryBtasAgencyList` |
| 中文名 | 查询btas质检机构列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/QueryBtasAgencyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2885 |
| 更新日期 | `2023-03-08` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id` | body | string | 否 | 店铺id，优先按店铺id查询 | `11123` |
| `supplier_id` | body | string | 否 | 供应商id | `23231` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/QueryBtasAgencyList?app_key=your_appkey_here&method=inspection.QueryBtasAgencyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `details` | array | 机构列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "details": [
      {
        "agency_id": "47",
        "agency_name": "采货侠"
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
