# install.ticket.operateIndustryTicket

> 行业服务操作工单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.ticket.operateIndustryTicket` |
| 中文名 | 行业服务操作工单 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/ticket/operateIndustryTicket` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5988 |
| 更新日期 | `2026-04-02` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ticketId` | body | string | 是 | 工单id | `7314871300083188022` |
| `operateTime` | body | string | 是 | 秒级时间戳 | `1703641182` |
| `operateContent` | body | string | 是 | 工单回复描述 | `操作完成` |
| `attachments` | body | array | 否 | 字段废弃，请使用attachmentList | `` |
| `  └ url` | body | string | 否 | url | `douyin.com` |
| `  └ type` | body | string | 否 | 附件类型：image-图片，video-视频 | `image` |
| `extend` | body | string | 否 | 预留 | `{}` |
| `operateCommandCode` | body | string | 是 | 回复-P1107(这个值写死) | `P1107` |
| `operator` | body | string | 否 | 操作人 | `test` |
| `attachmentList` | body | array | 否 | 附件 | `` |
| `  └ type` | body | string | 否 | 附件类型：image-图片，video-视频 | `image` |
| `  └ url` | body | string | 否 | url | `https:` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.ticket.operateIndustryTicket&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 500:ticket_not_exist（sub_code: isv.business-failed:500） | 500:ticket_not_exist |

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
  "sub_code": "isv.business-failed:500",
  "sub_msg": "500:ticket_not_exist"
}
```

## 备注
