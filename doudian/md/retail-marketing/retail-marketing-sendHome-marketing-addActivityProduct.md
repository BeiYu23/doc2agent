# 为创建好的营销活动门店绑定商品

> sendHome.marketing.addActivityProduct — 为创建好的营销活动门店绑定商品

| 元信息 | 值 |
| --- | --- |
| 中文名 | 为创建好的营销活动门店绑定商品 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-sendHome-marketing-addActivityProduct` |
| 接口 ID | `doudian.retail-marketing.sendHome.marketing.addActivityProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6807 |
| 更新日期 | `2024-08-28` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | string | 否 | 营销活动id | `123` |
| `store_id` | body | mixed | 否 | 门店id | `123` |
| `create_details` | body | array | 否 | 新增明细 一次请求最多新增50条数据 | `` |
| `  └ main_product_id` | body | string | 否 | 主商品id | `123` |
| `  └ sub_product_id` | body | string | 否 | 子商品id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sendHome.marketing.addActivityProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `success_detail_list` | array | 成功明细 | `` |
| `fail_detail_list` | array | 失败明细 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |

## 响应示例

成功：

```json
{
  "data": {
    "fail_detail_list": [
      {
        "fail_reason": "abc",
        "main_product_id": "123",
        "sub_product_id": "123"
      }
    ],
    "success_detail_list": [
      {
        "main_product_id": "123",
        "sub_product_id": "123"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
