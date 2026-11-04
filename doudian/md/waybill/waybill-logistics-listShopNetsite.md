# logistics.listShopNetsite

> 本接口可以查询商家和物流商的订购关系以及物流单号使用情况

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.listShopNetsite` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/listShopNetsite` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1843 |
| 更新日期 | `2023-03-20` |

## 接口说明

- 文档书: 电子面单API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 是 | 物流服务商编码（想获取全量物流，则传空字符串） | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `netsites` | array | 商家已开通的网点列表信息 | `` |
| `logistics_code` | string | 快递公司编码 | `zhongtong` |
| `company_type` | string | 物流服务商业务类型 1：直营  2：加盟 3：落地配 4：直营带网点 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 4006:店铺ID非法（sub_code: isv.business-failed:4006） | 请检查您的店铺id是否正确 |

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
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "4006:店铺ID非法"
}
```

## 备注
