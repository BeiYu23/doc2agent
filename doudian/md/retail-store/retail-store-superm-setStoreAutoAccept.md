# superm.setStoreAutoAccept

> 设置门店自动接单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.setStoreAutoAccept` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/setStoreAutoAccept` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2965 |
| 更新日期 | `2023-09-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | number | 是 | 门店id | `123321` |
| `op_type` | body | string | 是 | 设置自动接单状态；open 开启 close  关闭 | `open` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/setStoreAutoAccept?app_key=your_appkey_here&method=superm.setStoreAutoAccept&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 店铺ID不能为空（sub_code: isv.missing-parameter:40011） | 请确认店铺ID参数格式正确 |
| `40002` | 缺少必选参数 / 门店ID不能为空（sub_code: isv.missing-parameter:40012） | 请确认门店ID参数格式正确 |
| `50002` | 业务处理失败 / 请输入正确的操作信息（sub_code: isv.business-failed:40100） | 请输入正确的操作信息 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20201） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统繁忙，请稍后重试（sub_code: isp.service-error:20112） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:50114） | store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 未开通平台运力服务（sub_code: isv.business-failed:50111） | 未开通平台运力服务 |

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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:40011",
  "sub_msg": "店铺ID不能为空"
}
```

## 备注
