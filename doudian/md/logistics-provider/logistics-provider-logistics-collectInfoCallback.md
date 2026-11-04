# logistics.collectInfoCallback

> 作为服务商确认接单的依据，在揽收前可多次更新，揽收之后取消会失败，快递员信息或者网点信息回传会驱动运单变为已接单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.collectInfoCallback` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/collectInfoCallback` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/4455 |
| 更新日期 | `2023-09-01` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `biz_type` | body | string | 是 | courier：快递员信息 netInfo：网点信息 all：全部 | `courier` |
| `operate_time` | body | number | 是 | 更新时间戳 | `1608556777` |
| `request_id` | body | string | 是 | 唯一码 | `1324535345646` |
| `waybill_code` | body | string | 是 | 运单号 | `SF1234567890` |
| `collect_info` | body | object | 是 | 揽收网点&快递员信息 | `` |
| `  └ courier_name` | body | string | 否 | 快递员名称 | `刘先生` |
| `  └ courier_tel` | body | string | 否 | 联系电话 | `1567902344` |
| `  └ net_code` | body | string | 否 | 网点编码 | `123455` |
| `  └ net_name` | body | string | 否 | 网点名称 | `测试网点` |
| `  └ net_tel` | body | string | 否 | 网点联系电话 | `1567902344` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/wmsInboundCallback?app_key=your_appkey_here&method=yunc.wmsInboundCallback&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | boolean | 请求结果 | `true` |
| `return_code` | string | 失败编码 | `10000` |
| `message` | string | 失败原因 | `系统错误` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:12702） | 根据错误信息检查请求参数 |
| `20000` | 系统错误（sub_code: isp.service-error:12704） | 联系平台研发定位 |
| `50002` | 业务处理失败 / 当前状态不允许变更（sub_code: isv.business-failed:12710） | 已揽收不允许更新 |
| `50002` | 业务处理失败 / 当前状态已取消不允许更新（sub_code: isv.business-failed:12714） | 当前状态已取消不允许更新 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": "data",
    "msg": "\"系统内部异常\""
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:12702",
  "sub_msg": "参数错误"
}
```

## 备注
