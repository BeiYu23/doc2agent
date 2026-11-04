# WMS回传增值服务单数据

> yunc.valueAddedOrderCallBack — WMS回传增值服务单数据

| 元信息 | 值 |
| --- | --- |
| 中文名 | WMS回传增值服务单数据 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-valueAddedOrderCallBack` |
| 接口 ID | `doudian.warehouse.yunc.valueAddedOrderCallBack` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/valueAddedOrderCallBack` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2536 |
| 更新日期 | `2025-12-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `value_added_order_no` | body | string | 是 | 增值服务单号 | `VA123456` |
| `event_type` | body | mixed | 是 | 事件类型 2-待审核 3-审核不通过 4-审核通过 5-作业中 6-已完成 | `1` |
| `warehouse_code` | body | string | 是 | 仓编号 | `W001` |
| `biz_order_no` | body | string | 是 | 唯一流水号 | `123456` |
| `occur_time` | body | mixed | 是 | 秒级时间戳 | `1664193365` |
| `operator` | body | string | 是 | 操作人 | `操作人A` |
| `details` | body | array | 否 | 增值服务详情 | `` |
| `  └ line_no` | body | string | 是 | 行号 | `SC123456_0` |
| `  └ actual_qty` | body | mixed | 是 | 实际数量 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/valueAddedOrderCallBack?app_key=your_appkey_here&method=yunc.valueAddedOrderCallBack&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 错误码 | `0` |
| `msg` | string | 异常信息 | `系统内部异常` |
| `data` | string | data | `data` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务端异常（sub_code: isp.service-error:1001） | 联系服务端研发排查 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1004） | 检查参数重新回传 |
| `50002` | 业务处理失败 / 仓库编码鉴权失败，操作仓和鉴权仓不一致（sub_code: isv.business-failed:1003） | 检查操作仓Code |
| `50002` | 业务处理失败 / 增值服务单不存在（sub_code: isv.business-failed:21000） | 检查增值服务单号后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "data",
    "msg": "系统内部异常"
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
  "sub_code": "isp.service-error:1001",
  "sub_msg": "服务端异常"
}
```

## 备注
