# 订购服务权益查询接口-服务市场

> rights.info — 订购服务权益查询接口-服务市场

| 元信息 | 值 |
| --- | --- |
| 中文名 | 订购服务权益查询接口-服务市场 |
| 文档地址 | `/docs/doudian/tool/tool-rights-info` |
| 接口 ID | `doudian.tool.rights.info` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/rights/info` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/352 |
| 更新日期 | `2023-08-01` |

## 接口说明

- 文档书: 工具API（版本 V6.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_type` | body | string | 否 | 授权主体类型，不传参默认查询店铺，2-ebill用户；3-供应商 | `3` |
| `outer_biz_id` | body | string | 否 | 外部业务ID(模板市场为模板code)，非必传，不可与service_id同传 | `6859718390706503687` |
| `service_id` | body | number | 否 | 抖店服务市场服务ID，非必传，不可与outer_biz_id同传 | `111111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/rights/info?app_key=your_appkey_here&method=rights.info&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `expire_time` | string | 权益到期时间 | `2022-02-01 11:22:11` |
| `rights_type` | string | 0-试用版，1-正式版 | `1` |
| `spec_type` | string | 规格类型，0-版本，其他待定 | `1` |
| `spec_val` | string | 规格名称 | `高级版` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 权益查询失败（sub_code: isv.business-failed:200） | 请核对应用与授权主体 |

## 响应示例

成功：

```json
{
  "data": {
    "expire_time": "2022-02-01 11:22:11",
    "rights_type": "1",
    "spec_type": "1",
    "spec_val": "高级版"
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
  "sub_code": "isv.business-failed:200",
  "sub_msg": "权益查询失败"
}
```

## 备注
