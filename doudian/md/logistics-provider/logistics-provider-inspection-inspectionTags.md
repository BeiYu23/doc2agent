# 需要给外部服务商提供一些订单/商品/商家等维度…

> inspection.inspectionTags — 需要给外部服务商提供一些订单/商品/商家等维度的标签数据查询，服务商会根据标签结果做对应的质检逻辑判定

| 元信息 | 值 |
| --- | --- |
| 中文名 | 需要给外部服务商提供一些订单/商品/商家等维度… |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-inspection-inspectionTags` |
| 接口 ID | `doudian.logistics-provider.inspection.inspectionTags` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/inspectionTags` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6926 |
| 更新日期 | `2024-10-16` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `order_code` | body | string | 是 | 订单码 | `1234566` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `tag_map` | string | 标签信息 key是标签的类型，value是标签的值 方便后面扩展，inspection_check_use_purchase_channel 表示质检结果是否依赖货品渠道，值为标准项的ID，反序列化后，不为空则认为不依赖;x_detection表示质检是否要过 X 光，反序列化后不为空（目前只有"true"值）表示要过 X 光 | `"tagMap": {         "inspection_check_use_purchase_channel": "[\"7369139374136492297\",\"7369139374136492297\"]","x_detection": "[\"true\"]"     },` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 质检任务不存在（sub_code: isv.business-failed:1006） | 联系研发 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:1006",
  "sub_msg": "质检任务不存在"
}
```

## 备注
