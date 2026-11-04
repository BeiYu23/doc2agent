# superm.createVirtualMobile

> 隐私小号获取

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.createVirtualMobile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/createVirtualMobile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2739 |
| 更新日期 | `2023-09-19` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | number | 是 | 店铺订单编号 | `店铺订单号` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/createVirtualMobile?app_key=your_appkey_here&method=superm.createVirtualMobile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `mobile_info` | object | 获取虚拟号返回结果信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 数据转换错误（sub_code: isv.business-failed:50202） | 请通过错误信息排查问题 |
| `20000` | 系统错误（sub_code: isp.service-error:20100） | 请通过错误信息排查问题 |
| `40004` | 非法的参数 / 非法的请求参数（sub_code: isv.parameter-invalid:40100） | 请确认请求参数是否正确 |
| `40002` | 缺少必选参数 / 缺失必传参数（sub_code: isv.missing-parameter:40000） | 请确认缺失的必传参数 |
| `50002` | 业务处理失败 / 配置信息错误（sub_code: isv.business-failed:50203） | 请排查配置信息错误 |
| `50002` | 业务处理失败 / 当前查询单据不存在：订单不存在（sub_code: isv.business-failed:20111） | 当前查询单据不存在：订单不存在 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:10036） | 系统繁忙，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "mobile_info": {
      "expire_time": "2022-11-07 20:00:00",
      "is_new_create": "true",
      "mobile_virtual": "1893434345-1234"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:50202",
  "sub_msg": "数据转换错误"
}
```

## 备注
