# logistics.interception.updateInterceptionInfo

> 用于服务商推送拦截状态

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.interception.updateInterceptionInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/3564 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `inner_shop_id` | body | mixed | 否 | 店铺ID | `1234` |
| `resource_code` | body | string | 否 | 资源编码 | `RC_XXXXX` |
| `waybill_no` | body | string | 否 | 运单号 | `1234567` |
| `return_result` | body | string | 否 | 结果：1-拦截/退回成功；2-拦截/退回失败 | `1` |
| `result_code` | body | string | 否 | 失败原因编码：（return_result=1时为空，return_result=2时必传） 拦截失败： 10000——运单号有误 10001——包裹未揽件 10002——包裹已派件 10003——包裹已签收 11404——系统异常 10004——包裹已终止 10005——快递商无法识别网点 10006——信息不全 10007——系统超时，请重新发起 10008——重复拦截 10009——物流轨迹异常 10010——收件地址不支持派送 10011——物流商资源编码有误 10012——派件网点增值服务异常 10013——其他 10014——网点不具备拦截能力 10015——非抖音电商电子面单 10016——拦截前已丢失 退回失败： 10001——用户签收 10002——包裹丢失 10003——包裹破损 10004——操作不规范（物理退回、逻辑未退回） 10005——包裹未退回发件站点 10006——取消拦截 10007——弃件 20000——其他 | `10001` |
| `result_message` | body | string | 否 | 拦截失败/退回失败原因（return_result=1时为空，return_result=2时必传；长度不能超过100英文字符，一个中文相当于3个英文字符） | `包裹未揽件` |
| `status` | body | mixed | 否 | 状态：（默认2——退回） 1——拦截 2——退回 | `1` |
| `operation_time` | body | string | 否 | 实操时间 | `2023-07-25 12:00:00` |
| `express` | body | string | 否 | 物流商编码： zhongtong——中通 jtexpress——极兔 yunda——韵达 shentong——申通 yuantong——圆通 | `zhongtong` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.interception.updateInterceptionInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 请检查参数的正确性 |
| `20000` | 系统错误 / 系统异常（sub_code: isp.service-error:10002） | 系统异常，请重试 |
| `50002` | 业务处理失败 / 当前状态不允许变更（sub_code: isv.business-failed:10006） | 当前状态不允许变更，不可重试 |

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
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "参数错误"
}
```

## 备注
