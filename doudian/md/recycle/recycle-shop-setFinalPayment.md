# shop.setFinalPayment

> 设置尾款信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.recycle.shop.setFinalPayment` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/setFinalPayment` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/68/1659 |
| 更新日期 | `2022-02-17` |

## 接口说明

- 文档书: 回收寄卖API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `final_price` | body | number | 是 | 尾款价格 | `12345` |
| `product_imgs` | body | array | 是 | 商品图片信息 | `https://tosv.boe.byted.org/obj/ecom-shop-material/v1_kjmqYuUBq_70574132456860388280201_818a633a4fcf03f65f4f7211adc34afa_sx_395228_www800-800` |
| `product_dscription` | body | string | 是 | 描述一下这个商品 | `非常热销的switch游戏手柄` |
| `shop_order_no` | body | string | 是 | 店铺单号 | `12345` |
| `operate_user_name` | body | string | 是 | 操作人信息 | `nishizhu95` |
| `source` | body | number | 否 | 0默认/1Open调用-创建/2Open调用-更新 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/setFinalPayment?app_key=your_appkey_here&method=shop.setFinalPayment&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
