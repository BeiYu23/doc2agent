# 白底图生成结果回传

> product.whiteBgImageGenResult.save — 白底图生成结果回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 白底图生成结果回传 |
| 文档地址 | `/docs/doudian/innovation/innovation-product-whiteBgImageGenResult-save` |
| 接口 ID | `doudian.innovation.product.whiteBgImageGenResult.save` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/whiteBgImageGenResult/save` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1543/6833 |
| 更新日期 | `2024-09-29` |

## 接口说明

- 文档书: 创新应用（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `result` | body | array | 否 | 优化结果 | `` |
| `  └ white_bg_image_url` | body | string | 否 | 白底图：素材中心url | `www.baidu.com` |
| `  └ product_id` | body | mixed | 否 | 商品id | `111` |
| `  └ success` | body | boolean | 否 | 是否成功 | `true` |
| `  └ failed_reason` | body | string | 否 | 失败原因 | `失败原因` |
| `task_id` | body | mixed | 是 | 任务id | `111` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/whiteBgImageGenResult/save?app_key=your_appkey_here&method=product.whiteBgImageGenResult.save&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 任务实例不存在（sub_code: isv.business-failed:2000001） | 检查任务是否存在 |
| `40004` | 非法的参数 / 入参非法（sub_code: isv.parameter-invalid:1000001） | 根据提示检查入参是否合法 |
| `20000` | 系统错误 / 系统错误，请稍后重试（sub_code: isp.service-error:1000002） | 系统错误，请稍后重试 |

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
