# 资金流水明细文件下载(境内

> order.downloadShopAccountItemFile — 资金流水明细文件下载(境内)

| 元信息 | 值 |
| --- | --- |
| 中文名 | 资金流水明细文件下载(境内 |
| 文档地址 | `/docs/doudian/bill/bill-order-downloadShopAccountItemFile` |
| 接口 ID | `doudian.bill.order.downloadShopAccountItemFile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/order/downloadShopAccountItemFile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/46/1433 |
| 更新日期 | `2025-06-27` |

## 接口说明

- 文档书: 账单API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `download_id` | body | string | 是 | 下载id，有效期24小时； | `DL202111041446472412450342` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/order/downloadShopAccountItemFile?app_key=your_appkey_here&method=order.downloadShopAccountItemFile&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `url` | string | 文件url，链接时效为1小时 | `https://lf9-tos-bill-center-sign.bytetos.com/ecom-YOUR_SECRET_KEY.csv?x-expires=1636012061&x-signature=yz1M9N%2BXGMtBXyMFT9O75buK26w%3D` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 下载记录不存在（sub_code: isv.parameter-invalid:100002） | 重新生成download_id去下载文件 |
| `50002` | 业务处理失败 / 文件还未生成（sub_code: isv.business-failed:100015） | 等待文件生成完成 |
| `50002` | 业务处理失败 / 下载文件失败（sub_code: isv.business-failed:100025） | 重新下载 |
| `40004` | 非法的参数 / 文件已经失效（sub_code: isv.parameter-invalid:100016） | 重新生成download_id去下载文件 |

## 响应示例

成功：

```json
{
  "data": {
    "url": "https://lf9-tos-bill-center-sign.bytetos.com/ecom-YOUR_SECRET_KEY.csv?x-expires=1636012061&x-signature=yz1M9N%2BXGMtBXyMFT9O75buK26w%3D"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:100002",
  "sub_msg": "下载记录不存在"
}
```

## 备注
