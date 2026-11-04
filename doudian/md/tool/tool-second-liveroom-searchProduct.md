# second.liveroom.searchProduct

> 根据关键词查询直播间商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.second.liveroom.searchProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7565 |
| 更新日期 | `2025-07-07` |

## 接口说明

- 文档书: 工具API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `anchorID` | body | mixed | 否 | 主播抖音账号UID | `123` |
| `productSearchKey` | body | string | 否 | 商品关键词 | `测试` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.liveroom.searchProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sale_num` | string | 已售数量 | `123` |
| `product_url` | string | 商品链接 | `test` |
| `product_id` | mixed | 商品ID | `123` |
| `product_name` | string | 商品名称 | `test` |
| `main_img` | string | 商品主图 | `test` |
| `sale_price` | string | 商品价格 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "main_img": "test",
    "product_id": "123",
    "product_name": "test",
    "product_url": "test",
    "sale_num": "123",
    "sale_price": "123"
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
