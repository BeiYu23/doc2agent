# 回传质检通过和价格

> recycle.qualityTestingResult — 回传质检通过和价格

| 元信息 | 值 |
| --- | --- |
| 中文名 | 回传质检通过和价格 |
| 文档地址 | `/docs/doudian/recycle/recycle-recycle-qualityTestingResult` |
| 接口 ID | `doudian.recycle.recycle.qualityTestingResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/qualityTestingResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/1885 |
| 更新日期 | `2021-09-03` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `recycle_price` | body | number | 否 | 回收价 | `11300` |
| `consignment_price` | body | number | 否 | 寄卖价 | `11300` |
| `clue_order_id` | body | number | 是 | 回收订单ID | `123` |
| `is_passed` | body | number | 是 | 是否通过 1: 通过 2:不通过 | `1` |
| `failed_reason` | body | number | 否 | 不通过必传 不通过理由 1 货品成色太差； 2 货品与线索单不一致；  3 货品为假； 4 协商一致退货； 5 其他。 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/qualityTestingResult?app_key=your_appkey_here&method=recycle.qualityTestingResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
