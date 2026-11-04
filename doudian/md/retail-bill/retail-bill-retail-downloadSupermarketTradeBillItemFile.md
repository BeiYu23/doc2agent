# 即时零售交易账单下载

> retail.downloadSupermarketTradeBillItemFile — 即时零售交易账单下载，在调用/retail/downloadSupermarketTradeBillItem接口拿到download_id后，通过本接口换取账单文件下载链接

| 元信息 | 值 |
| --- | --- |
| 中文名 | 即时零售交易账单下载 |
| 文档地址 | `/docs/doudian/retail-bill/retail-bill-retail-downloadSupermarketTradeBillItemFile` |
| 接口 ID | `doudian.retail-bill.retail.downloadSupermarketTradeBillItemFile` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/retail/downloadSupermarketTradeBillItemFile` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1518/7185 |
| 更新日期 | `2024-12-30` |

## 接口说明

- 文档书: 账单管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `download_id` | body | string | 否 | 下载id； | `DL202412301518521716454401` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comcrossborder/msg/push?app_key=your_appkey_here&method=crossborder.msg.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | string | 返回code 100000为成功, 返回100015 时表示文件生成中，请稍后再试，其他状态码均为失败 | `100000` |
| `code_msg` | string | 返回信息描述，失败状态下会有失败描述 | `SUCCESS` |
| `url` | string | 文件url，链接时效为1小时 | `https://lf9-tos-bill-center-sign.bytetos.com/ecom-YOUR_SECRET_KEY.csv?x-expires=1636012061&x-signature=yz1M9N%2BXGMtBXyMFT9O75buK26w%3D` |

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
