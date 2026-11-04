# medicine.getPrescriptionOrder

> 基于处方单查询订单状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.hospital.medicine.getPrescriptionOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/getPrescriptionOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/5993 |
| 更新日期 | `2023-12-28` |

## 接口说明

- 文档书: 互联网医院（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `prescription_no` | body | string | 是 | 外部处方单编号 | `no213213131` |
| `hospital_name` | body | string | 是 | 互联网医院名称 | `测试医院` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/wms/inboundDetailNotify?app_key=your_appkey_here&method=wms.inboundDetailNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `prescription` | object | 处方单信息 | `` |
| `sku_orders` | array | 关联订单信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 50004:处方单不存在（sub_code: isv.business-failed:50004） | 50004:处方单不存在 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:50004",
  "sub_msg": "50004:处方单不存在"
}
```

## 备注
