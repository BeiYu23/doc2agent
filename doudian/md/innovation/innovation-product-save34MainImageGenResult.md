# 回传3:4主图生成结果

> product.save34MainImageGenResult — 回传3:4主图生成结果

| 元信息 | 值 |
| --- | --- |
| 中文名 | 回传3:4主图生成结果 |
| 文档地址 | `/docs/doudian/innovation/innovation-product-save34MainImageGenResult` |
| 接口 ID | `doudian.innovation.product.save34MainImageGenResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/save34MainImageGenResult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1543/6831 |
| 更新日期 | `2024-09-29` |

## 接口说明

- 文档书: 创新应用（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `result` | body | array | 否 | 优化结果 | `` |
| `  └ product_id` | body | mixed | 否 | 商品id | `111` |
| `  └ three_to_four_image_list` | body | array | 否 | 主图 商品主图3:4 跟商品编辑接口入参格式保持一致 | `[imageUrl1,imageUrl1,imageUrl1]` |
| `  └ success` | body | boolean | 否 | 是否成功 | `true` |
| `  └ failed_reason` | body | string | 否 | 失败原因 | `失败原因` |
| `task_id` | body | mixed | 否 | 任务id | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/save34MainImageGenResult?app_key=your_appkey_here&method=product.save34MainImageGenResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:1000001） | 请检查入参 |
| `50002` | 业务处理失败 / 任务不存在（sub_code: isv.business-failed:2000001） | 请检查入参taskId是否合法 |

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
  "sub_code": "isv.business-failed:1000001",
  "sub_msg": "参数错误"
}
```

## 备注
