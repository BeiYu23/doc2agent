# instantShopping.updateSpuGoodsInfo

> 支持仓储服务商回传货品基础信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.instantShopping.updateSpuGoodsInfo` |
| 中文名 | 支持仓储服务商回传货品基础信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/7127 |
| 更新日期 | `2024-12-04` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `goods_id` | body | string | 是 | 抖音测Goodd货品ID | `1231223` |
| `gross_length` | body | mixed | 否 | 毛长 | `1000` |
| `gross_width` | body | mixed | 否 | 毛宽 | `1000` |
| `gross_height` | body | mixed | 否 | 毛高 | `1000` |
| `gross_weight` | body | mixed | 否 | 毛重 | `1000` |
| `temperature_layer` | body | mixed | 否 | 仓存储温层： 1：冷冻(-18~-23) 5：冷藏(0~4) 10：恒温(10~15) 20：室温 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.updateSpuGoodsInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数不正确（sub_code: isv.parameter-invalid:40001） | 调整为正确参数 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "参数不正确"
}
```

## 备注
