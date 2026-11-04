# 商家ERP通过调用接口审核处方单

> medicine.updatePrescriptionStatusByInterface — 商家ERP通过调用接口审核处方单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商家ERP通过调用接口审核处方单 |
| 文档地址 | `/docs/doudian/prescription/prescription-medicine-updatePrescriptionStatusByInterface` |
| 接口 ID | `doudian.prescription.medicine.updatePrescriptionStatusByInterface` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/updatePrescriptionStatusByInterface` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1479/6463 |
| 更新日期 | `2024-05-07` |

## 接口说明

- 文档书: 商家处方药（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `memeber_id` | body | number | 是 | 成员id | `12321312` |
| `belong_shop_id` | body | number | 是 | 药剂师所属店铺id | `123123123` |
| `uid` | body | number | 是 | 药剂师uid | `12312312` |
| `prescription_id` | body | number | 是 | 处方单id | `123123123` |
| `status` | body | string | 是 | 状态，1:通过，2:拒绝 | `2` |
| `note` | body | string | 是 | 拒绝理由 | `不详细` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.commarketing/membership/bind/v1?app_key=your_appkey_here&method=marketing.membership.bind.v1&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 没有权限（sub_code: isp.service-error:100002） | 检查药剂师是否是有对应处方单审核权限 |
| `50002` | 业务处理失败 / -1:系统错误，请稍后重试（sub_code: isv.business-failed:-1） | -1:系统错误，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "integral": "100",
    "level": "1"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:100002",
  "sub_msg": "没有权限"
}
```

## 备注
