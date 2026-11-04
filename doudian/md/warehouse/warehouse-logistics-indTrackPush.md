# logistics.indTrackPush

> 即时配轨迹推送接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.logistics.indTrackPush` |
| 中文名 | 即时配轨迹推送 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/indTrackPush` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2109 |
| 更新日期 | `2022-10-09` |

## 接口说明

- 文档书: 仓库作业API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cur_time` | body | string | 是 | 请求时间 | `2022-04-28 10:17:54` |
| `company` | body | string | 是 | 公司编码 | `powertestexpress` |
| `trace_msgs` | body | array | 是 | 轨迹信息 | `` |
| `  └ track_no` | body | string | 是 | 运单号 | `87878100070426001` |
| `  └ traces` | body | array | 是 | 轨迹列表 | `` |
| `    └ opcode` | body | string | 是 | 事件编码 | `ORDER_RECEIVED` |
| `    └ op_time` | body | string | 是 | 事件操作时间 | `2022-04-28 14:17:54` |
| `    └ content` | body | string | 是 | 文案 | `骑手已送到` |
| `    └ rider` | body | object | 否 | 骑手信息 | `` |
| `      └ name` | body | string | 是 | 骑手姓名 | `张三` |
| `      └ mobile` | body | string | 是 | 骑手电话号码 | `18888888888` |
| `    └ third_party_company` | body | string | 否 | 三方运力公司，顺丰同城 sftc 闪送 shansong 达达 dada UU uupt 美团 meituan 蜂鸟 fengniao | `sftc` |
| `    └ exception_code` | body | string | 否 | 异常编码,“1001” 联系不上门店 “1002” 门店地址错误 “2001” 联系不上顾客 “2002” 顾客地址错误 “2003” 更改顾客配送地址 “3001” 托寄物损坏 “3002” 托寄物丢失 “4001” 服务商系统异常 “5001” 内部系统异常 “9000” 其他分类 “9999” 未知分类 | `1001` |
| `    └ exception_desc` | body | string | 否 | 异常原因 | `联系不上门店` |
| `    └ cancel_code` | body | string | 否 | 取消编码，“1000” 商户原因取消 “2000” 消费者原因取消 “3000” 骑手原因取消 “4000” 即时配公司原因取消 | `1000` |
| `    └ cancel_desc` | body | string | 否 | 取消原因 | `商户原因取消` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/indTrackPush?app_key=your_appkey_here&method=logistics.indTrackPush&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:-10001） | 检查入参 |
| `40004` | 非法的参数 / company参数错误（sub_code: isv.parameter-invalid:-20005） | 检查入参 |

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
  "sub_code": "isv.parameter-invalid:-10001",
  "sub_msg": "参数错误"
}
```

## 备注
