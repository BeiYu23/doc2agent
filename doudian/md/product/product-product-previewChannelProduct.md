# product.previewChannelProduct

> 预览渠道品信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.previewChannelProduct` |
| 中文名 | 预览渠道品信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/previewChannelProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/4467 |
| 更新日期 | `2025-09-08` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `main_product_id` | body | mixed | 是 | 主商品ID | `3631654780608339610` |
| `channel_id` | body | mixed | 是 | 渠道ID | `1775199232748660` |
| `channel_type` | body | mixed | 是 | 渠道类型 | `3` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/previewChannelProduct?app_key=your_appkey_here&method=product.previewChannelProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `main_product_id` | mixed | 主商品ID | `3631654780608339610` |
| `channel_id` | mixed | 渠道ID | `1775199232748660` |
| `channel_type` | mixed | 渠道类型 | `3` |
| `name` | string | 渠道品标题，包含标题前缀+标题内容 | `半身裙` |
| `start_time` | string | 有效期开始时间 | `2023-02-21 16:46:21` |
| `end_time` | string | 有效期结束时间 | `2023-02-21 16:46:21` |
| `price_follow_main` | boolean | 价格是否跟随主品 | `true` |
| `share_main_stock` | boolean | 库存是否与主品共享 | `true` |
| `is_kol_exclusive` | boolean | 是否『达人专属』渠道品 | `true` |
| `status` | mixed | 渠道品状态 0：下架 2：上架 3：封禁 | `1` |
| `channel_buy_limit` | object | 限购信息 | `` |
| `sku_channel` | array | SKU信息 | `` |
| `main_img_material` | object | 渠道品主图信息 | `` |
| `detail_brief_material` | object | 渠道品详情图信息 | `` |
| `freight_template` | object | 运费模板配置 | `` |
| `sku_code_follow_main` | boolean | 商家编码与主品保持一致配置，true-与主品保持一致，false-自定义 | `false` |
| `check_status` | mixed | 渠道品审核状态，1：未提交审核；2：审核中；3：审核通过；4：审核拒绝 | `3` |
| `name_prefix` | string | 标题前缀 | `标题前缀` |
| `name_subject` | string | 标题内容 | `标题内容` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 商品不存在或已彻底删除（sub_code: isv.business-failed:2010058） | 商品不存在或已彻底删除 |
| `50002` | 业务处理失败 / 渠道品查询失败，请重试（sub_code: isv.business-failed:2010001） | 渠道品查询失败，请重试 |
| `50002` | 业务处理失败 / 查询品牌信息失败（sub_code: isv.business-failed:2010013） | 查询品牌信息失败 |
| `50002` | 业务处理失败 / 渠道类型不合法（sub_code: isv.business-failed:2010004） | 渠道类型不合法 |
| `50002` | 业务处理失败 / 110103019:渠道品不存在（sub_code: isv.business-failed:110103019） | 110103019:渠道品不存在 |

## 响应示例

成功：

```json
{
  "data": {
    "channel_buy_limit": {
      "max_buy_num": "2",
      "min_buy_num": "1",
      "total_buy_num": "5"
    },
    "channel_id": "1775199232748660",
    "channel_type": "3",
    "check_status": "3",
    "detail_brief_material": {
      "img_list": "[\"xxxx\", \"xxxx\"]",
      "material_status": "1",
      "material_type": "18",
      "reject_reason": "不清晰"
    },
    "end_time": "2023-02-21 16:46:21",
    "freight_template": {
      "freight_follow_main": "true",
      "freight_id": "0"
    },
    "is_kol_exclusive": "true",
    "main_img_material": {
      "img_list": "[\"xxxx\", \"xxxx\"]",
      "material_status": "1",
      "material_type": "18",
      "reject_reason": "不清晰"
    },
    "main_product_id": "3631654780608339610",
    "name": "半身裙",
    "name_prefix": "标题前缀",
    "name_subject": "标题内容",
    "price_follow_main": "true",
    "share_main_stock": "true",
    "sku_channel": [
      {
        "name": "红色",
        "sku_channel": {
          "code": "11111",
          "price": "1111",
          "sku_id": "12323232132",
          "stock_num": "11"
        },
        "sku_id": "12323232132",
        "sku_main": {
          "price": "1111",
          "stock": "11"
        },
        "status": "1"
      }
    ],
    "sku_code_follow_main": "false",
    "start_time": "2023-02-21 16:46:21",
    "status": "1"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2010058",
  "sub_msg": "商品不存在或已彻底删除"
}
```

## 备注
