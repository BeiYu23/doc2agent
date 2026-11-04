# product.digest

> 查询商品摘要信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.product.digest` |
| 中文名 | 查询商品摘要信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/digest` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/7513 |
| 更新日期 | `2025-07-22` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 否 | 商品id | `1` |
| `product_shop_id` | body | mixed | 否 | 店铺id | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/digest?app_key=your_appkey_here&method=product.digest&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_info` | object | 商品信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "product_info": {
      "images": "[\"https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_e27a4a730d92e07142f41f06835d61ac_sx_78806_www800-800\"]",
      "main_img": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_e27a4a730d92e07142f41f06835d61ac_sx_78806_www800-800",
      "name": "短裙女士dkt-超舒适",
      "product_id": "1749781773",
      "sale_price": "100",
      "sell_num": "10",
      "sellable": "true",
      "status": "0",
      "update_time": "1749781773",
      "white_back_ground_pic": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/jpeg_m_e27a4a730d92e07142f41f06835d61ac_sx_78806_www800-800"
    }
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
