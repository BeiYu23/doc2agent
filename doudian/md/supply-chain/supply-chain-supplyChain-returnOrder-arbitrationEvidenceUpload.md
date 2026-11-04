# supplyChain.returnOrder.arbitrationEvidenceUpload

> 供应商上传仲裁举证

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.returnOrder.arbitrationEvidenceUpload` |
| 中文名 | 供应商上传仲裁举证 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6475 |
| 更新日期 | `2024-04-26` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_no` | body | string | 是 | 仲裁单号 | `ARB23063015122546` |
| `gsh_no` | body | string | 是 | 售后单号 | `GSH23063014385884` |
| `arbitration_evidence` | body | array | 否 | 供应商证据 | `["我没有不发货"]` |
| `arbitration_explain` | body | string | 否 | 供应商对于仲裁的解释说明 | `我对仲裁有异议` |
| `extends` | body | string | 否 | 证据扩展字段 | `{}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.returnOrder.arbitrationEvidenceUpload&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | 操作是否成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:1000） | 重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1020） | 重新填写入参 |

## 响应示例

成功：

```json
{
  "data": {
    "success": "true"
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
  "sub_code": "isv.business-failed:1000",
  "sub_msg": "业务处理失败"
}
```

## 备注
