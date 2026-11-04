# coupons.cancelVerify

> 卡券取消核销接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.coupon.coupons.cancelVerify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/coupons/cancelVerify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/52/668 |
| 更新日期 | `2025-09-10` |

## 接口说明

- 文档书: 卡券API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cert_no` | body | string | 是 | 卡号券码 | `231342sdd` |
| `batch_no` | body | string | 否 | 幂等请求编号 | `123123` |
| `cancel_verify_count` | body | mixed | 否 | 取消核销总次数 | `3` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/cancelVerify?app_key=your_appkey_here&method=coupons.cancelVerify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:000002） | 参数错误 |
| `20000` | 系统错误 / 数据库访问异常（sub_code: isp.service-error:030001） | 数据库访问异常 |
| `50002` | 业务处理失败 / QueryCertInfo cert verifyCount check error（sub_code: isv.business-failed:010009） | 010009:QueryCertInfo cert verifyCount check error |
| `50002` | 业务处理失败 / 卡号错误（sub_code: isv.business-failed:010021） | 卡号错误,请检查 |
| `50002` | 业务处理失败 / QueryCertInfo cert status check error（sub_code: isv.business-failed:10002） | 010002:QueryCertInfo cert status check error |
| `50002` | 业务处理失败 / 010016:卡券已冻结（sub_code: isv.business-failed:010016） | 010016:卡券已冻结 |
| `50002` | 业务处理失败 / 030002:数据处理失败（sub_code: isv.business-failed:30002） | 030002:数据处理失败 |
| `50002` | 业务处理失败 / 并发请求,请稍后重试（sub_code: isv.business-failed:10029） | 并发请求,请稍后重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:000002",
  "sub_msg": "参数错误"
}
```

## 备注
