# retail.afterSale.getNegotiation

> 查询到家售后协商详情

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-refund.retail.afterSale.getNegotiation` |
| 中文名 | 查询到家售后协商 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1548/6897 |
| 更新日期 | `2024-09-23` |

## 接口说明

- 文档书: 售后管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_id` | body | mixed | 否 | 使用售后单ID查询协商信息，可以为空，after_sale_id与negotiate_id二者必传其一 | `146611545747612686` |
| `negotiate_id` | body | string | 否 | 使用协商ID查询协商信息，可以为空，after_sale_id与negotiate_id二者必传其一 | `723064074982170901` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=retail.afterSale.getNegotiation&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `negotiation_form` | string | 协商方案的内容，key为协商ID | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务系统异常-不可重试的错误（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常-可重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入必填参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |

## 响应示例

成功：

```json
{
  "data": {
    "negotiation_form": {}
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
  "sub_code": "isv.business-failed:5000001",
  "sub_msg": "业务系统异常-不可重试的错误"
}
```

## 备注
