# mini.author.windowProductSchema

> 获取达人橱窗商品 schema

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.author.windowProductSchema` |
| 中文名 | 获取达人橱窗商品 schema |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/author/windowProductSchema` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6925 |
| 更新日期 | `2024-10-08` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `author_id` | body | mixed | 是 | 达人uid | `777` |
| `user_id` | body | string | 是 | 抖音c端用户open id | `888` |
| `product_id` | body | mixed | 是 | 商品id | `3544316315726671982` |
| `micro_app_id` | body | string | 是 | 小程序 appId | `tt12312894712894` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/author/windowProductSchema?app_key=your_appkey_here&method=mini.author.windowProductSchema&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_schema` | string | 商详页链接 | `sslocal://ec_goods_pdp?biz_context=%7B%22author_id%22%3A%222430379999917452%22%2C%22sec_author_id%22%3A%22MS4wLjABAAAA8h8aoimC_MmfFJp-AAB6bxHQaFMYtrfhbeHwtqdrD-nNnfr_4vuI23AKuGRI%22%2C%22same_product_scene%22%3A0%2C%22hot_sale_type%22%3A0%7D&chain_info=%7B%22ecom_entrance_form%22%3A%22products%22%2C%22enter_from%22%3A%22store_page%22%2C%22ecom_scene_id%22%3A%221004%22%2C%22enter_method%22%3A%22click_store_product%22%2C%22carr---` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 606010000:入参UserId非法（sub_code: isv.business-failed:606010000） | 请检查入参 |

## 响应示例

成功：

```json
{
  "data": {
    "product_schema": "sslocal://ec_goods_pdp?biz_context=%7B%22author_id%22%3A%222430379999917452%22%2C%22sec_author_id%22%3A%22MS4wLjABAAAA8h8aoimC_MmfFJp-AAB6bxHQaFMYtrfhbeHwtqdrD-nNnfr_4vuI23AKuGRI%22%2C%22same_product_scene%22%3A0%2C%22hot_sale_type%22%3A0%7D&chain_info=%7B%22ecom_entrance_form%22%3A%22products%22%2C%22enter_from%22%3A%22store_page%22%2C%22ecom_scene_id%22%3A%221004%22%2C%22enter_method%22%3A%22click_store_product%22%2C%22carr---"
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
  "sub_code": "isv.business-failed:606010000",
  "sub_msg": "606010000:入参UserId非法"
}
```

## 备注
