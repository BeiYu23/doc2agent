# trade.TopSearchQueryPredict

> 商品标题热搜词推荐

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.trade.TopSearchQueryPredict` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/trade/TopSearchQueryPredict` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2677 |
| 更新日期 | `2022-11-03` |

## 接口说明

- 文档书: 商品API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 否 | 叶子类目ID；通过【/shop/getShopCategory】接口获取，填写错误id接口返回为空。 | `25108` |
| `image` | body | object | 否 | 首图信息 | `` |
| `  └ image_url` | body | string | 否 | 首图url，url公网可访问地址即可。 | `"https://p9-aio.ecombdimg.com/obj/ecom-shop-material/vGQQPXed_m_00512396211e8d0f6d4cacecea4597e7_sx_138896_www960-960"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/coupons/cancelVerify?app_key=your_appkey_here&method=coupons.cancelVerify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | array | 推荐热搜词 | `['面料', '防油', '防水', '围裙', '工作服', '成人', '围腰', '罩衣', '时尚', '无袖', '做饭', '家用', '韩版', '防污', '透气', '背带', '薄款', '可爱', '袖套', '洋气']` |

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
