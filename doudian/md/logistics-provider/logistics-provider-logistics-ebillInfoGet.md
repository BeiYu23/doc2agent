# logistics.ebillInfoGet

> 面单明文信息查询接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.ebillInfoGet` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/ebillInfoGet` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2886 |
| 更新日期 | `2024-08-07` |

## 接口说明

- 文档书: 物流商API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 是 | 电子面单号 | `UT2900675235553` |
| `company` | body | string | 否 | 物流公司编码 | `shunfeng` |
| `user_type` | body | mixed | 是 | 请求用户类型，1-系统；2-业务员（快递员）；3-客服；4-总部业务人员；5-网点业务人员 | `1` |
| `system_source` | body | string | 是 | 系统来源，根据物流公司内部系统的代号传值，比如CRM系统，网点操作系统、小件员APP等，区分系统唯一性 | `1` |
| `query_reason` | body | string | 是 | 查询原因，根据实际用户查询的情况传值，如派件员联系收件人；处理客诉问题等 | `处理客诉问题` |
| `ip_address` | body | string | 否 | IP地址，调用该接口数据的用户的IP地址 | `10.10.10.10` |
| `user_id` | body | string | 否 | 若userType≠1时，则必须传入具体用户的系统ID，可以结合systemSource中的系统的用户ID | `1234` |
| `net_code` | body | string | 否 | 查询用户的所属机构编码 | `1234` |
| `net_name` | body | string | 否 | 查询用户的所属机构名称 | `1234` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/ebillInfoGet?app_key=your_appkey_here&method=logistics.ebillInfoGet&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | - | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10014:运单号不存在（sub_code: isv.business-failed:10014） | - |
| `50002` | 业务处理失败 / 11704：当前用户单日明文查询量已耗尽，请联系平台运营处理（sub_code: isv.business-failed:11704） | - |
| `50002` | 业务处理失败 / 11703：当日明文查询量已耗尽，请联系平台物流运营护理（sub_code: isv.business-failed:11703） | - |
| `50002` | 业务处理失败 / 4006:waybillCode不能为空（sub_code: isv.business-failed:4006） | 请检查waybillCode入参 |
| `50002` | 业务处理失败 / 11705:物流风险查询,已拦截！（sub_code: isv.business-failed:11705） | 本次请求被拦截，如有需要请联系物流商总部处理 |

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
  "sub_code": "isv.business-failed:10014",
  "sub_msg": "10014:运单号不存在"
}
```

## 备注
