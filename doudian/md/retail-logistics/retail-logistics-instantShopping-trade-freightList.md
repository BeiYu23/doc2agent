# instantShopping.trade.freightList

> 即时零售运费模板查询列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-logistics.instantShopping.trade.freightList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1530/7422 |
| 更新日期 | `2025-06-06` |

## 接口说明

- 文档书: 物流发货API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `size` | body | string | 否 | 每页返回数量 | `10` |
| `name` | body | string | 否 | 模板名称搜索 | `包邮` |
| `page` | body | string | 否 | 页码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.trade.freightList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `List` | array | 返回结果 | `` |
| `Count` | mixed | 模板数量 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 获取运费模板列表失败，请稍后重试（sub_code: isp.service-error:20013） | 获取运费模板列表失败，请稍后重试 |
| `50002` | 业务处理失败 / 20012:size参数格式错误（sub_code: isv.business-failed:20012） | 请检查size参数格式 |
| `50002` | 业务处理失败 / 20011:page参数格式错误（sub_code: isv.business-failed:20011） | 请检查page参数格式 |
| `50002` | 业务处理失败 / 422:搜索超过最大字数限制（sub_code: isv.business-failed:422） | 请检查参数 |
| `50002` | 业务处理失败 / 500:查询运费模版失败（sub_code: isv.business-failed:500） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "Count": "10",
    "List": [
      {
        "template": {
          "calculate_type": "2",
          "fixed_amount": "0",
          "id": "1",
          "product_city": "110000",
          "product_province": "11",
          "rule_type": "6",
          "template_name": "包邮"
        }
      }
    ]
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:20013",
  "sub_msg": "获取运费模板列表失败，请稍后重试"
}
```

## 备注
