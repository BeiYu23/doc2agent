# sendHome.msgComponent.getToken

> 获取消息组件token

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.sendHome.msgComponent.getToken` |
| 中文名 | 获取消息组件token |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/6750 |
| 更新日期 | `2024-08-21` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 否 | 门店id，如果不传默认用总店维度获取消息 | `123` |
| `outer_store_id` | body | string | 否 | 外部门店编码，如果传了store_id优先使用store_id | `abc` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/iop/waybillReturn?app_key=your_appkey_here&method=iop.waybillReturn&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `token` | string | 消息组件token | `abcde` |
| `expire_time` | mixed | 过期时间戳 秒级 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 5000001:未查询到门店组织信息（sub_code: isv.business-failed:5000001） | 5000001:未查询到门店组织信息 |

## 响应示例

成功：

```json
{
  "data": {
    "delivery_id": "982734",
    "pack_list": [
      {
        "company_code": "jd",
        "deliver_id": "982734",
        "ship_num": "1",
        "track_no": "12345"
      }
    ],
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:5000001",
  "sub_msg": "5000001:未查询到门店组织信息"
}
```

## 备注
