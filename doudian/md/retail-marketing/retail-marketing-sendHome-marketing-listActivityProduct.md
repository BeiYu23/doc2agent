# 查询营销活动门店绑定的商品

> sendHome.marketing.listActivityProduct — 查询营销活动门店绑定的商品

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询营销活动门店绑定的商品 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-sendHome-marketing-listActivityProduct` |
| 接口 ID | `doudian.retail-marketing.sendHome.marketing.listActivityProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/6811 |
| 更新日期 | `2024-08-27` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `status` | body | mixed | 否 | 活动绑定商品状态 Init = 10,           // 创建中 Fail = 20,           // 创建失败 Delete = 40,         // 删除 PartialSuccess = 50, // 部分成功 Success = 90,        // 创建成功 | `10` |
| `main_product_ids` | body | array | 否 | 主商品列表 | `{123}` |
| `sub_product_ids` | body | array | 否 | 子商品列表 | `{123}` |
| `store_ids` | body | array | 否 | 门店id，用于多选 | `{123}` |
| `page` | body | mixed | 否 | 页码 | `1` |
| `size` | body | mixed | 否 | 页大小 | `20` |
| `activity_id` | body | string | 否 | 活动id | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=sendHome.marketing.listActivityProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 总数 | `10` |
| `data` | array | 主商品列表 | `` |

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
    "data": [
      {
        "create_time": "123",
        "detail_status": "10",
        "detail_status_reason": "abc",
        "main_product": {
          "id": "123",
          "img": "url",
          "name": "abc"
        },
        "store": {
          "shop_address": "abc",
          "shop_id": "123",
          "shop_name": "abc"
        },
        "sub_product": {
          "id": "123",
          "img": "url",
          "name": "abc"
        },
        "update_time": "123"
      }
    ],
    "total": "10"
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
