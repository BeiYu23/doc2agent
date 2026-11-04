# recycle.logisticsBack

> 回收商退货发货

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.recycle.logisticsBack` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/recycle/logisticsBack` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/1889 |
| 更新日期 | `2021-09-03` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `clue_order_id` | body | number | 是 | 线索单id | `6995829284321640492` |
| `company` | body | string | 是 | 物流公司 | `shunfeng` |
| `company_code` | body | string | 是 | 物流公司编码 | `shunfeng` |
| `logistics_code` | body | string | 是 | SF00000003 | `快递单号` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/recycle/logisticsBack?app_key=your_appkey_here&method=recycle.logisticsBack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success` | string | 是否成功 | `true` |
| `err_no` | string | 10002 | `错误编码` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "err_no": "错误编码",
    "success": "true"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
