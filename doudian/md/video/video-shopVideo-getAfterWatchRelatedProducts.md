# shopVideo.getAfterWatchRelatedProducts

> 获取搜后承接商品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.getAfterWatchRelatedProducts` |
| 中文名 | 获取搜后承接商品列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/getAfterWatchRelatedProducts` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8138 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query` | body | string | 否 | 商品ID或商品名称 | `宠物秋冬带帽菱` |
| `page_info` | body | object | 否 | 分页信息 | `` |
| `  └ page_size` | body | mixed | 否 | 页大小 | `10` |
| `  └ page_no` | body | mixed | 否 | 当前页码 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/getAfterWatchRelatedProducts?app_key=your_appkey_here&method=shopVideo.getAfterWatchRelatedProducts&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回结果 | `` |
| `msg` | string | 错误信息 | `success` |
| `code` | mixed | 错误码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "product_list": [
        {
          "product_info": {
            "category_name_list": "女装",
            "detail_h5_url": "https://xxx",
            "product_id": "1212121",
            "product_image": "https://xxx",
            "product_name": "宠物秋冬带帽菱形格卫",
            "product_status": "0",
            "sale_price": "1000",
            "shop": {
              "shop_id": "121212",
              "shop_logo": "https://xxx",
              "shop_name": "测试店铺"
            }
          },
          "stock": "100"
        }
      ],
      "total": "100"
    },
    "msg": "success"
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
