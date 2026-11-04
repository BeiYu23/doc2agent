# power.updateTicket

> 工单处理回传

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.updateTicket` |
| 中文名 | 工单处理回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/updateTicket` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1477 |
| 更新日期 | `2023-02-24` |

## 接口说明

- 文档书: 物流发货API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ticket_id` | body | string | 是 | 字节工单ID | `12345` |
| `track_no` | body | string | 否 | 运单号 | `1111` |
| `op_type` | body | string | 是 | 操作类型： handle 处理 | `handle` |
| `op_time` | body | number | 是 | 操作时间 | `12345678` |
| `remark` | body | string | 是 | 处理备注 | `备注` |
| `compensate_state` | body | string | 否 | 是否赔付， 1未赔付 2已赔付 | `1` |
| `compensate_amount` | body | number | 否 | 赔付金额，单位为分。在compensate_state为2是必填 | `111` |
| `compensate_reason` | body | string | 否 | 赔付原因： lose 丢失 damage 破损 other 其他 | `lose` |
| `attachment` | body | array | 否 | 附件链接 | `["http://www.toutiao.com"]` |
| `extension` | body | string | 否 | 扩展字段JSON 格式:{k1:v1,k2:v2} | `{}` |
| `handle_response` | body | string | 否 | 处理结果 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000:该工单不存在（sub_code: isv.business-failed:10000） | - |
| `50002` | 业务处理失败 / 10003:工单已处理，无法进行操作（sub_code: isv.business-failed:10003） | - |

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
  "sub_code": "isv.business-failed:10000",
  "sub_msg": "10000:该工单不存在"
}
```

## 备注
