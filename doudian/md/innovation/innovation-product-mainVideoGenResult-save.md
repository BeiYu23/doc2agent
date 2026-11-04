# 主图视频生成结果回传

> product.mainVideoGenResult.save — 主图视频生成结果回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 主图视频生成结果回传 |
| 文档地址 | `/docs/doudian/innovation/innovation-product-mainVideoGenResult-save` |
| 接口 ID | `doudian.innovation.product.mainVideoGenResult.save` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/mainVideoGenResult/save` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1543/6834 |
| 更新日期 | `2024-09-29` |

## 接口说明

- 文档书: 创新应用（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `result` | body | array | 否 | 优化结果 | `` |
| `  └ main_video_id` | body | string | 否 | 主图视频id：素材中心视频id | `12222` |
| `  └ product_id` | body | mixed | 否 | 商品id | `122222` |
| `  └ success` | body | boolean | 否 | 是否成功 | `true` |
| `  └ failed_reason` | body | string | 否 | 失败原因 | `查询热搜词失败` |
| `task_id` | body | mixed | 是 | 任务id | `11111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/mainVideoGenResult/save?app_key=your_appkey_here&method=product.mainVideoGenResult.save&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 任务实例不存在（sub_code: isv.business-failed:2000001） | 任务实例不存在 |
| `40004` | 非法的参数 / 入参mainVideoId非法（sub_code: isv.parameter-invalid:1000001） | 入参mainVideoId非法 |

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
  "sub_code": "isv.business-failed:2000001",
  "sub_msg": "任务实例不存在"
}
```

## 备注
