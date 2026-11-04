# 查询短视频可关联商品列表

> shopVideo.listRelatableProduct — 查询短视频可关联商品列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询短视频可关联商品列表 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-listRelatableProduct` |
| 接口 ID | `doudian.video.shopVideo.listRelatableProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/listRelatableProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7149 |
| 更新日期 | `2024-12-19` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id_list` | body | array | 否 | 商品id列表 | `[1234567]` |
| `sell_num_start` | body | mixed | 否 | 销量左区间 | `10` |
| `sell_num_end` | body | mixed | 否 | 销量右区间 | `100` |
| `page` | body | mixed | 是 | 页码 | `1` |
| `page_size` | body | mixed | 是 | 每页数量 | `10` |
| `category_id_list` | body | array | 否 | 类目id列表 | `34` |
| `product_name` | body | string | 否 | 商品名称 | `衬衫` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/listRelatableProduct?app_key=your_appkey_here&method=shopVideo.listRelatableProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `product_list` | array | 商品列表 | `` |
| `total` | mixed | 总数 | `100` |
| `page` | mixed | 当前页 | `1` |
| `page_size` | mixed | 每页数量 | `20` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `10001` | 请求部分失败 / 查询商品失败（sub_code: isv.business-part-failed:628004001） | 稍后重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 根据提示文案调整请求参数 |

## 响应示例

成功：

```json
{
  "data": {
    "page": "1",
    "page_size": "20",
    "product_list": [
      {
        "check_status": "3",
        "draft_status": "1",
        "img": "https://p3-aio.ecombdimg.com/obj/ecom-shop-material/lyRChMMc_m_2edc6702f8657f0b60ff6c4e0c8cf0ac_sx_38948_www720-720",
        "market_price": "10000",
        "name": "衬衫",
        "product_id": "1234567",
        "status": "0",
        "stock_num": "3"
      }
    ],
    "total": "100"
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
  "code": 10001,
  "msg": "请求部分失败",
  "sub_code": "isv.business-part-failed:628004001",
  "sub_msg": "查询商品失败"
}
```

## 备注
