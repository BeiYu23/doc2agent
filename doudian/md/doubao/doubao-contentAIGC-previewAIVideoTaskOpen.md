# contentAIGC.previewAIVideoTaskOpen

> 预校验成片参数与积分，不占用额度

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.doubao.contentAIGC.previewAIVideoTaskOpen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/contentAIGC/previewAIVideoTaskOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1627/8657 |
| 更新日期 | `2026-09-23` |

## 接口说明

- 文档书: 豆包工作（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 待生成商品 ID。 | `` |
| `params` | body | object | 是 | 当前已选成片参数。 | `` |
| `  └ paradigm_key` | body | string | 否 | 已选范式标识。 | `` |
| `  └ resolution` | body | string | 否 | 已选分辨率。 | `` |
| `  └ model_code` | body | string | 否 | 模型编码；未指定时由服务端按默认规则选择。 | `` |
| `  └ target` | body | mixed | 否 | 已选成片目标，复用现有枚举。 | `` |
| `  └ duration` | body | object | 否 | 已选时长档位，复用配置查询中的定义。 | `` |
| `    └ max_seconds` | body | mixed | 是 | 档位最大时长，单位秒；不小于 minSeconds。 | `` |
| `    └ min_seconds` | body | mixed | 是 | 档位最小时长，单位秒。 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/contentAIGC/previewAIVideoTaskOpen?app_key=your_appkey_here&method=contentAIGC.previewAIVideoTaskOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `required_credits` | mixed | 本次预计实际消耗积分，免费为 0；可生成时必返，无法计算时缺省。 | `` |
| `available_credits` | mixed | 成功时必返，当前剩余可用积分。 | `` |
| `reason` | string | 不可生成时返回原因；余额不足且可算费用时仍返回 requiredCredits。 | `` |
| `base_resp` | object | 正常校验不通过与依赖查询失败分开处理。 | `` |
| `can_create` | boolean | 成功时必返，当前条件下是否可生成；不占用额度或积分。 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:1000000） | 请稍后重试；创建任务重试时请保持原 requestId 不变。若持续失败，请联系技术支持。 |
| `40004` | 非法的参数 / 请求参数错误（sub_code: isv.parameter-invalid:1000001） | 请按接口文档检查必填字段、参数类型及取值后重试。 |

## 响应示例

成功：

```json
{
  "data": {
    "available_credits": "0",
    "base_resp": {
      "extra": {},
      "status_code": "0",
      "status_message": ""
    },
    "can_create": "0",
    "reason": "",
    "required_credits": "0"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:1000000",
  "sub_msg": "系统异常"
}
```

## 备注
