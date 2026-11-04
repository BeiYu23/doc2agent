# buyin.updateSampleConfs

> 批量设置达人买样返款规则

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.updateSampleConfs` |
| 中文名 | 批量设置达人买样返款规则 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/updateSampleConfs` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/5908 |
| 更新日期 | `2023-12-14` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_sample_configs` | body | array | 是 | 达人买样返款设置 | `` |
| `  └ product_id` | body | mixed | 是 | 商品 id | `34312324232145` |
| `  └ buy_style` | body | mixed | 是 | 商品是否支持达人买样返款；1-支持达人买样返款，2-不支持达人买样返款。除特殊类目（虚拟充值、奢侈品、汽车整车、二手类目）外其他所有商品需填 1，特殊类目商品可自主选择是否支持达人买样返款 | `1` |
| `  └ buy_volume_limit` | body | mixed | 否 | 达人买样返款订单量门槛，值需在3-10000范围内。达人带货结算订单量≥所设订单量，返还达人买样全款；如果不支持达人买样返款此字段无意义 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/updateSampleConfs?app_key=your_appkey_here&method=buyin.updateSampleConfs&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `failed_reason` | string | 部分处理失败的商品id和对应原因 | `null` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 查询商品信息失败（sub_code: isv.parameter-invalid:-1025） | 输入的商品 id 有误 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:-1） | 根据报错信息调整参数 |

## 响应示例

成功：

```json
{
  "data": {
    "failed_reason": {}
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
  "sub_code": "isv.parameter-invalid:-1025",
  "sub_msg": "查询商品信息失败"
}
```

## 备注
