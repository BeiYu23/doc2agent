# alliance.card.add

> 添加商品(精选联盟商品)到达人选品车

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.tool.alliance.card.add` |
| 中文名 | 添加商品(精选联盟商品)到达人选品车 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/card/add` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/162/7600 |
| 更新日期 | `2025-07-16` |

## 接口说明

- 文档书: 工具API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `keep_picksource` | body | boolean | 否 | 是否保留商品链接原有选品来源，默认不保留（加选品车时默认会生成新的选品来源参数覆盖旧参数，转链的自定义参数也会失效，选品来源为当前加选品车应用），keep_picksource 为 true 时保留原有选品来源 | `true` |
| `products` | body | array | 否 | 商品信息，最多20个商品 | `` |
| `  └ product_id` | body | mixed | 否 | 商品ID | `3450632721376902816` |
| `  └ activity_url` | body | string | 否 | 团长活动商品URL | `https://haohuo.jinritemai.com/views/product/detail?ins_activity_param=eLee5v2&id=3424454103747684585` |
| `pick_extra` | body | string | 否 | 自定义参数，携带到订单（只允许 数字、字母和_，限制长度为20） | `test` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/card/add?app_key=your_appkey_here&method=alliance.card.add&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 请求结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "results": [
        {
          "bind_reason": "添加失败原因",
          "content": "弹窗信息",
          "failed_add_code": "1",
          "product_id": "3450632721376902816"
        }
      ],
      "total": "10"
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
