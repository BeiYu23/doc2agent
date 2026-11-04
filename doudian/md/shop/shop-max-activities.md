# 批量获取活动信息

> max.activities — 批量获取活动信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 批量获取活动信息 |
| 文档地址 | `/docs/doudian/shop/shop-max-activities` |
| 接口 ID | `doudian.shop.max.activities` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/max/activities` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/2836 |
| 更新日期 | `2025-09-22` |

## 接口说明

- 文档书: 店铺API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_ids` | body | array | 否 | 活动id，手动配置的时候传，数量最多50个 | `111,222` |
| `activity_type` | body | mixed | 是 | 活动类型，7-限时限量购，100-店铺满减 | `7` |
| `m_config_type` | body | mixed | 是 | 配置类型 0 手动配置，1 智能配置，默认手动配置，（目前不支持智能配置） | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/max/activities?app_key=your_appkey_here&method=max.activities&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `status_code` | mixed | 状态码 | `0` |
| `status_msg` | string | 状态说明 | `success` |
| `data` | object | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 啊哦，服务器打瞌睡了，再试一次吧～（sub_code: isp.service-error:4） | 再试一次 |
| `40004` | 非法的参数 / 参数不合法（sub_code: isv.parameter-invalid:5） | 检查参数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "full_discount_list": [
        {
          "activity_discounts": [
            {
              "condition_type": "2",
              "condition_value": "200",
              "discount": "100",
              "discount_id": "222",
              "discount_type": "3"
            }
          ],
          "activity_id": "222",
          "activity_name": "满减活动",
          "activity_type": "100",
          "condition_type": "2",
          "condition_value": "200",
          "discount": "100",
          "discount_id": "222",
          "discount_type": "3",
          "end_time": "1670566000000",
          "pre_start_time": "1670567000000",
          "products": [
            {
              "category_id": "数码3C",
              "check_status": "3",
              "main_img_url": "aaa",
              "name": "苹果手机",
              "original_price": "200",
              "product_id": "111",
              "product_type": "0",
              "sale_price": "100",
              "sell_num": "200",
              "status": "0"
            }
          ],
          "start_time": "1670568000000",
          "status": "0"
        }
      ],
      "time_buy_list": [
        {
          "activity_id": "111",
          "activity_name": "限时限量购活动",
          "activity_type": "7",
          "create_time": "1670566000000",
          "end_time": "1670569000000",
          "pre_start_time": "1670567000000",
          "products": [
            {
              "left_stock": "180",
              "max_sku_price": "120",
              "min_sku_price": "100",
              "product_base": {
                "category_leaf_id": "20000",
                "check_status": "3",
                "name": "苹果手机",
                "original_price": "200",
                "pic": "https://p9-aio.ecombdimg.com/obj/ecom-shop-material/v1_xPfNJOkX_71153427046487984750183_661ff1f563801d97f382e0ac114a09e6_sx_805824_www933-933",
                "product_id": "1111",
                "product_type": "0",
                "sale_price": "190",
                "sell_num": "100",
                "status": "0"
              },
              "sale_status": "1",
              "total_stock": "200"
            }
          ],
          "start_time": "1670568000000",
          "status": "0",
          "ts": "1670566000000"
        }
      ]
    },
    "status_code": "0",
    "status_msg": "success"
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
  "sub_code": "isp.service-error:4",
  "sub_msg": "啊哦，服务器打瞌睡了，再试一次吧～"
}
```

## 备注
