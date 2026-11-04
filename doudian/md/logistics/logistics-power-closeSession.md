# 客服关闭会话

> power.closeSession — 客服关闭会话

| 元信息 | 值 |
| --- | --- |
| 中文名 | 客服关闭会话 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-closeSession` |
| 接口 ID | `doudian.logistics.power.closeSession` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/closeSession` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1562 |
| 更新日期 | `2023-02-24` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `sessionId` | body | string | 是 | - | `111111` |
| `actionTime` | body | string | 是 | - | `123456789` |
| `dealerId` | body | string | 否 | - | `111` |
| `company` | body | string | 否 | - | `powerTest` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/closeSession?app_key=your_appkey_here&method=power.closeSession&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:10003） | 无 |

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
  "sub_code": "isv.business-failed:10003",
  "sub_msg": "业务处理失败"
}
```

## 备注
