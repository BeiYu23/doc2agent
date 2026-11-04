# 服务商回复工单

> power.operateTicket — 服务商回复工单

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回复工单 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-power-operateTicket` |
| 接口 ID | `doudian.logistics-provider.power.operateTicket` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/operateTicket` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2993 |
| 更新日期 | `2023-02-27` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ticketId` | body | string | 是 | 工单号 | `7204346045755982115` |
| `trackNo` | body | string | 否 | 运单号 | `7204346045755` |
| `opType` | body | string | 是 | 第一次处理：handle 第二次处理：appeal/noappeal | `handle` |
| `opTime` | body | number | 是 | 操作时间 | `1677478601` |
| `remark` | body | string | 是 | 处理备注 | `处理完成` |
| `compensateState` | body | string | 否 | 是否赔付，  1 未赔付  2 已赔付 | `1` |
| `compensateAmount` | body | number | 否 | 赔付金额，单位为分。在compensate_state为2是必填 | `1000` |
| `compensateReason` | body | string | 否 | 赔付原因：  lose 丢失  damage 破损  other 其他 | `lose` |
| `attachment` | body | array | 否 | 附件 | `["www.baidu.com"]` |
| `extension` | body | string | 否 | 扩展字段 | `{"key":"value"}` |
| `company` | body | string | 否 | 服务商编码 | `powertestexpress` |
| `handleResponse` | body | string | 否 | 处理结果： 1 认责 2 不认责 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/operateTicket?app_key=your_appkey_here&method=power.operateTicket&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 如参数不合法、工单id不存在等（sub_code: isv.business-failed:10000） | - |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:10002） | - |
| `50002` | 业务处理失败 / 当前的工单，物流商已经处理完成，不需要操作（sub_code: isv.business-failed:10003） | - |
| `50002` | 业务处理失败 / 禁止处理其他家物流商的工单（sub_code: isv.business-failed:10004） | - |
| `50002` | 业务处理失败 / 由于接口下发失败或者工单没有通过接口下发，需要物流商在协同平台处理（sub_code: isv.business-failed:10005） | - |

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
  "sub_msg": "如参数不合法、工单id不存在等"
}
```

## 备注
