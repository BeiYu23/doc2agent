# contentAIGC.createAIVideoTaskOpen

> 创建成片任务，同次提交按 requestId 幂等

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.doubao.contentAIGC.createAIVideoTaskOpen` |
| 中文名 | 创建成片任务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/contentAIGC/createAIVideoTaskOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1627/8658 |
| 更新日期 | `2026-09-23` |

## 接口说明

- 文档书: 豆包工作（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 待生成商品 ID。 | `` |
| `params` | body | object | 是 | 用户确认的成片参数，复用预校验中的定义。 | `` |
| `  └ target` | body | mixed | 否 | 已选成片目标，复用现有枚举。 | `` |
| `  └ paradigm_key` | body | string | 否 | 已选范式标识。 | `` |
| `  └ model_code` | body | string | 否 | 模型编码；未指定时由服务端按默认规则选择。 | `` |
| `  └ resolution` | body | string | 否 | 已选分辨率。 | `` |
| `  └ duration` | body | object | 否 | 已选时长档位，复用配置查询中的定义。 | `` |
| `    └ min_seconds` | body | mixed | 是 | 档位最小时长，单位秒。 | `` |
| `    └ max_seconds` | body | mixed | 是 | 档位最大时长，单位秒；不小于 minSeconds。 | `` |
| `request_id` | body | string | 是 | 首次提交前生成的幂等标识；同一次提交重试保持不变。 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/contentAIGC/createAIVideoTaskOpen?app_key=your_appkey_here&method=contentAIGC.createAIVideoTaskOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_id` | string | 成功时必返；重复提交相同请求返回原任务 ID，不重复生成。 | `` |
| `base_resp` | object |  | `` |

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
    "base_resp": {
      "extra": {},
      "status_code": "0",
      "status_message": ""
    },
    "task_id": ""
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
