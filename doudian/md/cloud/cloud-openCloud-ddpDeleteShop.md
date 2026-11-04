# 数据推送，删除绑定的推送店铺

> openCloud.ddpDeleteShop — 数据推送，删除绑定的推送店铺

| 元信息 | 值 |
| --- | --- |
| 中文名 | 数据推送，删除绑定的推送店铺 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-ddpDeleteShop` |
| 接口 ID | `doudian.cloud.openCloud.ddpDeleteShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/ddpDeleteShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/1403 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 电商云API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_id` | body | string | 是 | 店铺id | `77977` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/ddpDeleteShop?app_key=your_appkey_here&method=openCloud.ddpDeleteShop&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 内部错误，请稍后重试（sub_code: isv.business-failed:701） | 请检查网络 |
| `50002` | 业务处理失败 / 参数非法（sub_code: isv.business-failed:602） | 请检查网络 |
| `50002` | 业务处理失败 / 函数流程错误（sub_code: isv.business-failed:812） | 请联系服务方 |
| `50002` | 业务处理失败 / 该用户没有操作权限（sub_code: isv.business-failed:807） | 请检查自身请求 |
| `50002` | 业务处理失败 / 该用户没有此应用权限（sub_code: isv.business-failed:808） | 请检查自身请求 |
| `50002` | 业务处理失败 / 该用户没有此数据库实例权限（sub_code: isv.business-failed:809） | 请检查自身请求 |
| `50002` | 业务处理失败 / 该用户没有此店铺权限（sub_code: isv.business-failed:810） | 请检查自身请求 |
| `50002` | 业务处理失败 / 此App已删除或被禁用（sub_code: isv.business-failed:811） | 请检查自身请求 |
| `50002` | 业务处理失败 / 该店铺已经添加到其他数据库实例（sub_code: isv.business-failed:62208201） | 无 |
| `50002` | 业务处理失败 / 该店铺不存在（sub_code: isv.business-failed:62208202） | 请检查自身请求 |
| `50002` | 业务处理失败 / 该店铺未对此应用授权（sub_code: isv.business-failed:62208203） | 请联系服务方 |
| `50002` | 业务处理失败 / 无效历史推送天数（sub_code: isv.business-failed:62208009） | 请检查自身请求 |
| `50002` | 业务处理失败 / 内部错误，请稍后重试（sub_code: isv.business-failed:10000000） | 请稍后重试 |

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
  "sub_code": "isv.business-failed:701",
  "sub_msg": "内部错误，请稍后重试"
}
```

## 备注
