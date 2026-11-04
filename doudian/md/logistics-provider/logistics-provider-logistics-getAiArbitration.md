# 查询预校验结果

> logistics.getAiArbitration — 查询预校验结果接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询预校验结果 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-getAiArbitration` |
| 接口 ID | `doudian.logistics-provider.logistics.getAiArbitration` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getAiArbitration` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8310 |
| 更新日期 | `2026-05-22` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ticketId` | body | string | 是 | 工单id | `7637053321475309874` |
| `useScene` | body | mixed | 是 | 工单场景 (1-正式判责；2-服务商预判责) | `2` |
| `taskId` | body | string | 是 | ai预判责任务id | `7628571632545792256` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getAiArbitration?app_key=your_appkey_here&method=logistics.getAiArbitration&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `arbitrationInfo` | object | 仲裁信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "arbitrationInfo": {
      "arbitrationBasis": "1. 用户投诉运单错误\\n2. 举证要求：用户投诉的是正向物流包裹，需提供用户本人描述此订单服务过程中的通话录音+通话记录或者内部外呼软件记录\\n3. 本次举证选用通话录音+通话记录的方式，判定举证有效，仲裁不成立",
      "arbitrationResult": {
        "key": "2",
        "value": "仲裁不成立"
      },
      "createTime": "1778221649",
      "rightTicketType": {
        "key": "11606",
        "value": "超时未取件"
      },
      "status": {
        "key": "1",
        "value": "成功"
      },
      "suggestedRemark": "经核实，物流商举证有效，已提供【通话录音、通话记录及物流系统订单截图】，用户反馈投诉的并非本寄件单的超时未取件问题，故此判责不成立",
      "taskId": "7637053321475309874",
      "ticketId": "7628571632545792256",
      "trackNo": "1331877778251"
    }
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
