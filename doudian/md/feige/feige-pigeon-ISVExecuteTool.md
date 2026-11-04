# pigeon.ISVExecuteTool

> 执行ISV客服工具的接口，支持执行各种客服相关的自动化工具和脚本

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.ISVExecuteTool` |
| 中文名 | 执行ISV客服工具的接口 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/ISVExecuteTool` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/7670 |
| 更新日期 | `2025-11-27` |

## 接口说明

- 文档书: 飞鸽API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `tool_code` | body | string | 是 | 工具code | `"BASIC_SCRIPT"` |
| `execute_params` | body | string | 否 | 工具执行参数，部分工具存在必传参数 | `"product_id_list": "[\"3740656536352063689\",\"3686240338055397653\"]"` |
| `script` | body | string | 否 | 回复话术（BASIC_SCRIPT工具必传） | `"您好"` |
| `biz_params_context` | body | object | 是 | 固定业务参数，有就传，部分工具存在必传参数 | `` |
| `  └ talk_id` | body | string | 是 | 子会话ID | `"7524598324482114"` |
| `  └ shop_order_id` | body | string | 否 | 商城订单ID | `"0"` |
| `  └ sku_order_id` | body | string | 否 | sku订单ID | `"0"` |
| `  └ after_sale_id` | body | string | 否 | 售后ID | `"0"` |
| `  └ product_id` | body | string | 否 | 产品ID | `"37608307150512459"` |
| `  └ msg_id` | body | string | 是 | 消息ID | `"18370601871002"` |
| `pigeon_biz_type` | body | mixed | 是 | 业务身份 | `2` |
| `pigeon_shop_id` | body | mixed | 是 | 飞鸽店铺ID | `14562951` |
| `biz_idempotent_no` | body | string | 是 | 工具执行幂等ID，过期时间2h | `"0217519571190490000717ab0:1837060187100"` |
| `trace_id` | body | string | 是 | 生命周期ID | `"0217511190490000ffff40a17ab0:1837100268"` |
| `doudian_open_id` | body | string | 是 | 执行对象ID，一般为消费者ID | `"104477413000"` |
| `ext` | body | string | 否 | 扩展字段 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/ISVExecuteTool?app_key=your_appkey_here&method=pigeon.ISVExecuteTool&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | string | 工具执行结果。SUCCESS or FAILED | `"SUCCESS"` |
| `trace_id` | string | 生命周期ID | `"0217511190490000ffff40a17ab0:1837100268"` |
| `biz_err` | object | 业务错误 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 工具执行参数异常（sub_code: isp.service-error:30001） | 检查工具参数配置是否正确 |
| `20000` | 系统错误 / 工具暂不支持（sub_code: isp.service-error:30002） | 确认工具是否已上线或支持 |
| `20000` | 系统错误 / 当前会话已使用过该工具（sub_code: isp.service-error:30003） | 检查会话状态或更换工具 |
| `20000` | 系统错误 / 工具执行失败（sub_code: isp.service-error:30004） | 查看执行日志定位原因 |
| `20000` | 系统错误 / 工具执行幂等（sub_code: isp.service-error:30005） | 确认是否重复调用或重复请求 |
| `20000` | 系统错误 / 工具预先校验失败（sub_code: isp.service-error:30006） | 检查前置条件或参数是否符合要求 |
| `20000` | 系统错误 / 工具执行参数异常（sub_code: isp.service-error:30007） | 检查参数完整性与格式 |
| `20000` | 系统错误 / 工具配置加载失败（sub_code: isp.service-error:31000） | 检查配置文件或资源是否正常 |
| `20000` | 系统错误 / 工具生命周期ID缺失（sub_code: isp.service-error:31001） | 确认生命周期ID是否正确传入 |
| `20000` | 系统错误 / 事件执行失败（sub_code: isp.service-error:31100） | 检查事件执行逻辑及日志 |
| `20000` | 系统错误 / 事件表达失败（sub_code: isp.service-error:31101） | 检查事件表达式配置及语法 |
| `20000` | 系统错误 / 事件参数校验失败（sub_code: isp.service-error:31102） | 检查事件参数是否完整及符合要求 |

## 响应示例

成功：

```json
{
  "data": {
    "biz_err": {
      "code": "0",
      "msg": "\"\""
    },
    "result": "\"SUCCESS\"",
    "trace_id": "\"0217511190490000ffff40a17ab0:1837100268\""
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
  "sub_code": "isp.service-error:30001",
  "sub_msg": "工具执行参数异常"
}
```

## 备注
