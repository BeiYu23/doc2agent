# medicine.getShopDruggist

> 商家ERP获取店铺下的药剂师

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.prescription.medicine.getShopDruggist` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/getShopDruggist` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1479/6462 |
| 更新日期 | `2024-04-29` |

## 接口说明

- 文档书: 商家处方药（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | number | 否 | 第几页（从1开始) | `1` |
| `page_size` | body | number | 否 | 每页几条数据，最大50 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=marketing.membership.unbind.v1&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `druggists` | array | 药剂师列表 | `` |
| `total` | number | 总数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
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
