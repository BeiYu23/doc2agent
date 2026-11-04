# order.downloadToShop

> 1、通过【/order/downloadSettleItemToShop】接口返回的download_id。调用接口生成文件下载的URL链接时效为1小时，失效后需重新调此接口获取新的链接。
2、如需非url下载方式请调用【/order/getSettleB

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.bill.order.downloadToShop` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/downloadToShop` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1193 |
| 更新日期 | `2022-09-28` |

## 接口说明

- 文档书: 账单API（版本 V2.09）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `download_id` | body | string | 是 | 生成的download_id | `DL202108191056192174226975` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 状态码    100000-成功   100002-下载记录不存在   100015-文件还未生成   100016-文件已经失效   100025-文件生成失败 | `100000` |
| `code_msg` | string | 状态说明 | `success` |
| `url` | string | 生成的下载链接，URL链接时效为1小时，失效后需重新调此接口获取新的链接。 | `https://lf6-tos-bill-center-sign.bytetos.com/ecom-YOUR_SECRET_KEY.csv?x-expires=1629345425&x-signature=iaiLmiwJbc%2FMNKFrS6RaHzbdNwU%3D` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 100015:文件还未生成成功（sub_code: isv.business-failed:100015） | 100015:文件还未生成成功 |

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
  "sub_code": "isv.business-failed:100015",
  "sub_msg": "100015:文件还未生成成功"
}
```

## 备注
