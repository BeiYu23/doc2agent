# crossborder.OrderInterception

> 服务商锁单结果回告

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cross-border.crossborder.OrderInterception` |
| 中文名 | 服务商锁单结果回告 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossborder/OrderInterception` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/920 |
| 更新日期 | `2021-09-07` |

## 接口说明

- 文档书: 跨境API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `vendor` | body | string | 是 | 服务商编码 | `GZJS` |
| `order_id` | body | string | 是 | 交易单号 | `1234` |
| `occurrence_time` | body | string | 是 | 节点发生时间 yyyy-MM-dd HH:mm:ss | `2021-09-07 20:00:00` |
| `status` | body | number | 是 | 节点状态 4：锁单成功 5：锁单失败 | `4` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossborder/OrderInterception?app_key=your_appkey_here&method=crossborder.OrderInterception&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | number | 响应状态码 | `0` |
| `msg` | string | 响应信息 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 接口调用异常，请重试，多次失败请人工反馈（sub_code: isp.service-error:1005） | 请稍后重试 |
| `50002` | 业务处理失败 / 回告节点时序有误，请先回告出库完成节点（sub_code: isv.business-failed:10002） | 请先回告出库完成节点 |
| `20000` | 系统错误 / 接口调用异常，请重试，多次失败请人工反馈（sub_code: isp.service-error:99999） | 请稍后重试 |
| `50002` | 业务处理失败 / 交易单已关闭，请核实交易单状态（sub_code: isv.business-failed:10003） | 请核实交易单状态 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "msg": "成功"
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
  "sub_code": "isp.service-error:1005",
  "sub_msg": "接口调用异常，请重试，多次失败请人工反馈"
}
```

## 备注
