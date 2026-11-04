# sms.saveCombineAudience

> 保存生产包交互规则，获取组合人群包

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.sms.sms.saveCombineAudience` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/sms/saveCombineAudience` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/163/7788 |
| 更新日期 | `2025-09-19` |

## 接口说明

- 文档书: 短信API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `desc` | body | string | 否 | 人群包描述 | `描述描述` |
| `audience_id` | body | string | 否 | 人群包id，不传则新建，传入则更新 | `12312` |
| `audience_name` | body | string | 否 | 组合人群包名称 | `人群包人群包` |
| `node_list` | body | array | 否 | 节点list | `` |
| `  └ produce_id` | body | string | 否 | 生产包id。nodeType=1时必传 | `1231` |
| `  └ node_type` | body | number | 否 | 1值 2运算符 | `1` |
| `  └ condition` | body | string | 否 | nodeType=2时必传 AND交集 OR并集 EXCEPT差集 LEFTPARENS左括号 RIGHTPARENS右括号 | `符合` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillUpdate?app_key=your_appkey_here&method=iop.waybillUpdate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `audience_id` | string | 组合人群包id | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "982734",
    "return_result": "true"
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
