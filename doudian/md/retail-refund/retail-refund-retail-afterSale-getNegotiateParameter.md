# 售后协商参数获取

> retail.afterSale.getNegotiateParameter — 售后协商参数获取

| 元信息 | 值 |
| --- | --- |
| 中文名 | 售后协商参数获取 |
| 文档地址 | `/docs/doudian/retail-refund/retail-refund-retail-afterSale-getNegotiateParameter` |
| 接口 ID | `doudian.retail-refund.retail.afterSale.getNegotiateParameter` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1548/6896 |
| 更新日期 | `2024-09-23` |

## 接口说明

- 文档书: 售后管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `after_sale_id` | body | number | 是 | 售后单id | `146571325876834067` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/instituteOrderColonel?app_key=your_appkey_here&method=buyin.instituteOrderColonel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `default_parameter` | object | 默认协商参数,与售后单上一致,商家需要修改后才能提交协商 | `` |
| `pre_after_sale_type_list` | array | 售后类型可选值 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 业务系统异常-不可重试的错误（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入必填参数 |
| `40004` | 非法的参数 / 参数类型错误（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `20000` | 系统错误 / 系统异常-可重试（sub_code: isp.service-error:5100002） | 系统异常，可尝试重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
