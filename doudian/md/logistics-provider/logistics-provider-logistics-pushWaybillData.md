# logistics.pushWaybillData

> 物流商推送非抖运单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.pushWaybillData` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushWaybillData` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6927 |
| 更新日期 | `2025-03-10` |

## 接口说明

- 文档书: 物流商API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_code` | body | string | 是 | 运单号 | `123` |
| `company` | body | string | 是 | 物流商编码（连接平台物流商必填） | `shunfeng` |
| `province` | body | string | 否 | 省份密文，加密规则（运单号+省份， sm3 hash算法生成），例如运单号1234567，云南省，密文是fa0fcc2df6207a7007a3d9a40314a8d29ecc81e42fb0d5e47987bf84d2c0c743 | `fa0fcc2df6207a7007a3d9a40314a8d29ecc81e42fb0d5e47987bf84d2c0c743` |
| `city` | body | string | 否 | 城市密文，加密规则（运单号+城市， sm3 hash算法生成），例如运单号1234567，曲靖市，密文是8649477408039bbdab5fb592d90449bd32e6dee4c86927d87dd50ca4ad791021 | `8649477408039bbdab5fb592d90449bd32e6dee4c86927d87dd50ca4ad791021` |
| `district` | body | string | 否 | 区县密文，加密规则（运单号+区县， sm3 hash算法生成），例如运单号1234567，区县明文是 富源县 ，密文是5613f9ead98fec9ff4834e8d4bbeca07d643e4fa794aabb688f7f7f2e080910c | `5613f9ead98fec9ff4834e8d4bbeca07d643e4fa794aabb688f7f7f2e080910c` |
| `street` | body | string | 否 | 街道密文，加密规则（运单号+街道， sm3 hash算法生成），例如运单号1234567，街道明文是 哈哈街道 ，密文是1fd6c1949b7283d3458f02d32f21d96399ddab5adc559eb84db8b39edca02ae2 | `1fd6c1949b7283d3458f02d32f21d96399ddab5adc559eb84db8b39edca02ae2` |
| `detail_address` | body | string | 否 | 详细地址密文，加密规则（运单号+详细地址， sm3 hash算法生成），例如运单号1234567，详细地址是 二小对面，密文是727eec2f0eb34e0bd71caa25f241132ffc83f4c35abab4a08aaa62de27b691b8 | `727eec2f0eb34e0bd71caa25f241132ffc83f4c35abab4a08aaa62de27b691b8` |
| `mobile` | body | string | 否 | 手机号，与phone二者必填其一。为虚拟号码时则传不含分机号的未脱敏的前11位主机号，非虚拟号时传未脱敏的11位完整号码；加密规则（运单号+手机号， sm3 hash算法生成），例如运单号1234567，手机号是 18867727373，密文是8f8bf5dcc4e444197756f43fcb0e596f8af2466b4bbe195cb9eb66d54a89759b | `8f8bf5dcc4e444197756f43fcb0e596f8af2466b4bbe195cb9eb66d54a89759b` |
| `phone` | body | string | 否 | 手机号，与mobile二者必填其一。为虚拟号码时则传不含分机号的未脱敏的前11位主机号，非虚拟号时传未脱敏的11位完整号码；加密规则（运单号+手机号， sm3 hash算法生成），例如运单号1234567，手机号是 18867727373，密文是8f8bf5dcc4e444197756f43fcb0e596f8af2466b4bbe195cb9eb66d54a89759b | `69b5c6366379824c02b843c9994969134e321553254d5a9ca5552be0857d9a68` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=order.shopOperate.getSkuReviewResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:4006） | 修正入参 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:4007） | 重试 |

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
  "sub_code": "isv.missing-parameter:4006",
  "sub_msg": "参数错误"
}
```

## 备注
