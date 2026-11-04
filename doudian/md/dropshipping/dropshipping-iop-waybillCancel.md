# 【厂商】取消电子面单

> iop.waybillCancel — 【厂商】取消电子面单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【厂商】取消电子面单 |
| 文档地址 | `/docs/doudian/dropshipping/dropshipping-iop-waybillCancel` |
| 接口 ID | `doudian.dropshipping.iop.waybillCancel` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/iop/waybillCancel` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/59/675 |
| 更新日期 | `2021-07-18` |

## 接口说明

- 文档书: 代发API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | number | 是 | 代打店铺id | `884334435345` |
| `company_code` | body | string | 是 | 物流服务商编码 | `jtexpress` |
| `track_no` | body | string | 是 | 运单号 | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillCancel?app_key=your_appkey_here&method=iop.waybillCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `return_result` | boolean | 返回结果 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 取消总数/取号总数超过最大比例（sub_code: isv.business-failed:88888） | 请检查取消总数/取号总数 |

## 响应示例

成功：

```json
{
  "data": {
    "return_result": "true"
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
  "sub_code": "isv.business-failed:88888",
  "sub_msg": "取消总数/取号总数超过最大比例"
}
```

## 备注
