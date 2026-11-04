# recycle.createPrice

> 上传估价

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.recycle.createPrice` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/createPrice` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/1883 |
| 更新日期 | `2021-09-03` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `is_agree` | body | boolean | 是 | 是否同意 | `true` |
| `clue_order_id` | body | string | 是 | 线索单ID | `4782813149182887526` |
| `recycle_price` | body | number | 否 | 回收价，单位分 is_agree为true的时候recycle_price和consignment_price至少传1个 用户到手价格。 | `4000` |
| `consignment_price` | body | number | 否 | 寄卖价，单位分 is_agree为true的时候recycle_price和consignment_price至少传1个 商家寄卖的价格，商家根据平台固定抽佣规则抽佣。 | `3000` |
| `refuse_reason` | body | string | 否 | 拒绝理由 1：货品成色差； 2：货品为假； 3：其他 | `1` |
| `remark` | body | string | 否 | 备注 | `测试` |
| `address_id` | body | number | 否 | 地址库id 可以通过/address/list接口获取 https://op.jinritemai.com/docs/api-docs/13/558 | `11111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/createPrice?app_key=your_appkey_here&method=recycle.createPrice&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 状态非法，不支持流转（sub_code: isv.business-failed:-1） | 请检查状态 |
| `50002` | 业务处理失败 / 价格参数错误（sub_code: isv.business-failed:10002） | 请检查价格参数信息 |

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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "状态非法，不支持流转"
}
```

## 备注
