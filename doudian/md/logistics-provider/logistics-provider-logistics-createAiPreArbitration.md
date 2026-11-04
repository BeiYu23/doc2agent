# logistics.createAiPreArbitration

> 创建AI预校验

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.createAiPreArbitration` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/createAiPreArbitration` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8311 |
| 更新日期 | `2026-06-09` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `opType` | body | string | 否 | 操作类型 handle处理，appeal 申诉 | `handle` |
| `opTime` | body | mixed | 否 | 操作时间 | `1778742224` |
| `attachment` | body | array | 否 | 附件链接（1.支持图片 2.不展示给消费者） | `[https://lf3-static.bytednsdoc.com/obj/eden-cn/qteh7plmvhpeuhbf/vs.png]` |
| `company` | body | string | 否 | 物流商编码 | `ems` |
| `handleResponse` | body | mixed | 否 | 处理结果 1.认责 2.不认责 | `1` |
| `ticketId` | body | string | 否 | 字节工单ID | `7639638117879906575` |
| `trackNo` | body | string | 否 | 运单号 | `1357711411111` |
| `remark` | body | string | 否 | 备注 | `备注内容` |
| `extension` | body | string | 否 | 扩展字段 | `''` |
| `compensateState` | body | mixed | 否 | 是否赔付, 1未赔付 2已赔付 | `1` |
| `compensateAmount` | body | mixed | 否 | 赔付金额，单位为分。在compensate_state为2是必填 | `100` |
| `compensateReason` | body | string | 否 | 赔付原因：  lose 丢失  damage 破损  other 其他 | `lose` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/createAiPreArbitration?app_key=your_appkey_here&method=logistics.createAiPreArbitration&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `taskId` | string | 任务id | `7637053321475309874` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10004） | 更新参数 |
| `20000` | 系统错误 / 判责失败（sub_code: isp.service-error:14001） | 重新触发请求 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:-1） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "taskId": "7637053321475309874"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:10004",
  "sub_msg": "参数错误"
}
```

## 备注
