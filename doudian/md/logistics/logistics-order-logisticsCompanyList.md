# order.logisticsCompanyList

> 获取快递公司列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.order.logisticsCompanyList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/logisticsCompanyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/541 |
| 更新日期 | `2023-05-18` |

## 接口说明

- 文档书: 物流发货API（版本 V2.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 物流公司信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 未知错误，请重试（sub_code: isp.service-error:60019） | 请重试请求 |
| `50002` | 业务处理失败 / 错误信息不固定，根据下游返回的信息提示做处理（sub_code: isv.business-failed:60124） | 根据下游返回的错误信息做处理 |
| `50002` | 业务处理失败 / 120005:系统繁忙，请稍后重试（sub_code: isv.business-failed:120005） | 120005:系统繁忙，请稍后重试 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:60019",
  "sub_msg": "未知错误，请重试"
}
```

## 备注
