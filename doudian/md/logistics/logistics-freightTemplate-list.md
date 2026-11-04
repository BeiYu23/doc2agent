# 获取运费模板列表

> freightTemplate.list — 获取运费模板列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取运费模板列表 |
| 文档地址 | `/docs/doudian/logistics/logistics-freightTemplate-list` |
| 接口 ID | `doudian.logistics.freightTemplate.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/freightTemplate/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/565 |
| 更新日期 | `2021-06-04` |

## 接口说明

- 文档书: 物流发货API（版本 V2.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | 运费模板名称，支持模糊搜索 | `模版1` |
| `page` | body | string | 否 | 页数（默认为0，第一页从0开始） | `0` |
| `size` | body | string | 否 | 每页模板数（默认为10），最大值是100 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/freightTemplate/list?app_key=your_appkey_here&method=freightTemplate.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `List` | array | 运费模版列表 | `` |
| `Count` | number | 总数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 获取运费模板列表失败，请稍后重试（sub_code: isp.service-error:20013） | 稍后重试 |
| `50002` | 业务处理失败 / 20012:size参数格式错误（sub_code: isv.business-failed:20012） | 请检查size参数格式 |
| `50002` | 业务处理失败 / 20011:page参数格式错误（sub_code: isv.business-failed:20011） | 请检查page参数格式 |
| `50002` | 业务处理失败 / 422:搜索超过最大字数限制（sub_code: isv.business-failed:422） | 请检查参数 |
| `50002` | 业务处理失败 / 500:查询运费模版失败（sub_code: isv.business-failed:500） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "Count": "1",
    "List": [
      {
        "template": {
          "calculate_type": "1",
          "fixed_amount": "1",
          "id": "1",
          "product_city": "\"320000\"",
          "product_province": "\"32\"",
          "rule_type": "1",
          "template_name": "模版示例",
          "transfer_type": "1"
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
