# supplyChain.updateConsign

> 供货单更新发货物流

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.updateConsign` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/updateConsign` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/1735 |
| 更新日期 | `2023-07-20` |

## 接口说明

- 文档书: 供销平台API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_no` | body | string | 是 | 供货单号 | `CT706899923423` |
| `tms_code` | body | string | 是 | 发货的物流商编码 | `shunfeng` |
| `tracking_no` | body | string | 是 | 发货的运单号 | `SF398235235235` |
| `old_tms_code` | body | string | 否 | 【必填】上一次发货的物流商编码或者空字符串 | `yunda` |
| `old_tracking_no` | body | string | 否 | 【必填】上一次发货的运单号或者空字符串 | `2212121241` |
| `new_ship_cnt` | body | string | 否 | 【非必填】只有在需要修改件数的时候才填写。当前不支持即修改运单，又修改件数。在修改件数时，新老运单需要填写一样的内容 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/updateConsign?app_key=your_appkey_here&method=supplyChain.updateConsign&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | boolean | true=调用成功 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:2000） | 请参考错误信息，或联系对接人员 |

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
  "sub_code": "isv.business-failed:2000",
  "sub_msg": "业务处理失败"
}
```

## 备注
