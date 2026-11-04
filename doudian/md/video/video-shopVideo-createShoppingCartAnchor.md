# shopVideo.createShoppingCartAnchor

> 创建挂车锚点

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.createShoppingCartAnchor` |
| 中文名 | 创建挂车锚点 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/createShoppingCartAnchor` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7487 |
| 更新日期 | `2025-06-03` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID | `122121` |
| `user_id` | body | string | 否 | 不传默认人店一体账号，支持渠道号 | `121221` |
| `title` | body | string | 否 | 小黄车标题 | `这是标题` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/createShoppingCartAnchor?app_key=your_appkey_here&method=shopVideo.createShoppingCartAnchor&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | string | 生成的锚点ID | `1212122` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 1000001:当前商家暂未绑号（sub_code: isv.business-failed:1000001） | 引导商家绑号 |
| `50002` | 业务处理失败 / 1000000:商品当前已下架，用户不可购买（sub_code: isv.business-failed:1000000） | 传入正确状态的商品 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "1212122"
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
  "sub_code": "isv.business-failed:1000001",
  "sub_msg": "1000001:当前商家暂未绑号"
}
```

## 备注
