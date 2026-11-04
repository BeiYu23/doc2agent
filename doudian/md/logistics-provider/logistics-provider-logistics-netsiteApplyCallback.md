# logistics.netsiteApplyCallback

> 电子面单服务订购审核回调函数；

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.netsiteApplyCallback` |
| 中文名 | 电子面单服务订购审核回调函数 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/netsiteApplyCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2804 |
| 更新日期 | `2022-12-06` |

## 接口说明

- 文档书: 物流商API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `book_id` | body | string | 是 | 订购id | `323123` |
| `result` | body | boolean | 是 | 审核结果 （通过-true, 不通过 - false） | `true` |
| `remark` | body | string | 否 | 审核意见，不通过是可以备注本字段 | `审核意见` |
| `company` | body | string | 否 | 物流商编码 | `shunfeng` |
| `action` | body | string | 否 | 1 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt?app_key=your_appkey_here&method=test.encrypt&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10501:不能重复审核（sub_code: isv.business-failed:10501） | 请检查请求参数 |
| `50002` | 业务处理失败 / 10003:该数据不存在，请检查后重试（sub_code: isv.business-failed:10003） | 10003:该数据不存在，请检查后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "0"
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
  "sub_code": "isv.business-failed:10501",
  "sub_msg": "10501:不能重复审核"
}
```

## 备注
