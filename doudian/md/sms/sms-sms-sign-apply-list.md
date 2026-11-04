# sms.sign.apply.list

> 查看短信签名申请单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.sign.apply.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/sign/apply/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/1523 |
| 更新日期 | `2026-03-24` |

## 接口说明

- 文档书: 短信API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sms_account` | body | string | 是 | 短信发送渠道，主要做资源隔离 | `1234` |
| `like` | body | string | 否 | 搜索 | `1` |
| `page` | body | mixed | 否 | 页码，默认0 | `0` |
| `size` | body | mixed | 否 | 每页大小，默认10 | `10` |
| `sms_sign_apply_id` | body | string | 否 | 申请单id | `444` |
| `version` | body | string | 否 | 版本号v2则走新链路 | `v2` |
| `shop_sub_account` | body | string | 否 | 商家消息组，不传则默认查询商家消息组 | `sjfeosa` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/apply/list?app_key=your_appkey_here&method=sms.sign.apply.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `100` |
| `apply_list` | array | 短信签名申请单列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 响应结果不符合预期（sub_code: isv.business-failed:628005100） | 请根据错误信息描述检查 |
| `20000` | 系统错误 / 628004205:Redis Get错误（sub_code: isp.service-error:628004205） | 系统错误，请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "apply_list": [
      {
        "sign": "abc",
        "sms_account": "1234",
        "sms_sign_apply_id": "2342341444",
        "status": "2",
        "status_remark": "签名重复"
      }
    ],
    "total": "100"
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
  "sub_code": "isv.business-failed:628005100",
  "sub_msg": "响应结果不符合预期"
}
```

## 备注
