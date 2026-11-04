# （update_interception_in…

> logistics.update_interception_info — /logistics/update_interception_info

| 元信息 | 值 |
| --- | --- |
| 中文名 | （update_interception_in… |
| 文档地址 | `/docs/doudian/warehouse/warehouse-logistics-update_interception_info` |
| 接口 ID | `doudian.warehouse.logistics.update_interception_info` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/update_interception_info` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2080 |
| 更新日期 | `2023-04-11` |

## 接口说明

- 文档书: 仓库作业API（版本 V2.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shopId` | body | number | 是 | 店铺Id | `1234` |
| `resourceCode` | body | string | 是 | 物流服务商资源编码 | `RC1234567890` |
| `waybillNo` | body | string | 是 | 运单号 | `1234567890000` |
| `returnResult` | body | string | 是 | 退回结果 1:退回成功 2:退回失败 | `1` |
| `resultCode` | body | string | 否 | 退回失败原因编码 | `10001` |
| `resultMessage` | body | string | 否 | 退回失败原因信息 | `用户签收` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
