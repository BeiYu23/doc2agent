# contentAIGC.getAIVideoOptionsOpen

> 查询商品成片配置选项

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.doubao.contentAIGC.getAIVideoOptionsOpen` |
| 中文名 | 查询商品成片配置选项 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/contentAIGC/getAIVideoOptionsOpen` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1627/8656 |
| 更新日期 | `2026-09-23` |

## 接口说明

- 文档书: 豆包工作（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 当前店铺的商品 ID，十进制正整数字符串。 | `` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/contentAIGC/getAIVideoOptionsOpen?app_key=your_appkey_here&method=contentAIGC.getAIVideoOptionsOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `model_options` | array | 以下字段参考GetAIVideoModelOptions 可选模型。 | `` |
| `resolution_options` | array | 可选输出清晰度，如 720p、1080p。 | `` |
| `total_duration_options` | array | 可选成片时长档位 | `` |
| `base_resp` | object |  | `` |
| `targets` | array | 支持的成片目标 | `` |
| `paradigms` | array | 参考RecallCreativeParadigms | `` |

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
    "model_options": [
      {
        "model_code": "",
        "model_name": ""
      }
    ],
    "paradigms": [
      {
        "description": "",
        "name": "",
        "paradigm_key": ""
      }
    ],
    "resolution_options": "[]",
    "targets": "[]",
    "total_duration_options": [
      {
        "max_seconds": "0",
        "min_seconds": "0"
      }
    ]
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
