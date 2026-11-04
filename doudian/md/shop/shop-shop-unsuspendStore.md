# shop.unsuspendStore

> 门店恢复营业

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.shop.shop.unsuspendStore` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/unsuspendStore` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2384 |
| 更新日期 | `2024-02-26` |

## 接口说明

- 文档书: 店铺API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店ID | `123` |
| `reason` | body | string | 否 | 恢复营业原因 | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/unsuspendStore?app_key=your_appkey_here&method=shop.unsuspendStore&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_code` | mixed | 返回错误码 | `0` |
| `ret_msg` | string | - | `-` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 8:门店不存在（sub_code: isv.business-failed:8） | 门店不存在 |
| `50002` | 业务处理失败 / 14:非正常营业或停业的门店不可恢复营业（sub_code: isv.business-failed:14） | 非正常营业或停业的门店不可恢复营业 |
| `50002` | 业务处理失败 / 1:参数错误（sub_code: isv.business-failed:1） | 检查参数 |
| `50002` | 业务处理失败 / 2:业务处理异常（sub_code: isv.business-failed:2） | 稍后重试 |
| `50002` | 业务处理失败 / 100:系统错误，请稍后重试（sub_code: isv.business-failed:100） | 稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "ret_code": "0",
    "ret_msg": "-"
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
  "sub_code": "isv.business-failed:8",
  "sub_msg": "8:门店不存在"
}
```

## 备注
