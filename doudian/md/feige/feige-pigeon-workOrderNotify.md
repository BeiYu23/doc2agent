# pigeon.workOrderNotify

> 更新或者存储工单

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.feige.pigeon.workOrderNotify` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/pigeon/workOrderNotify` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/188/1974 |
| 更新日期 | `2022-10-27` |

## 接口说明

- 文档书: 飞鸽API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `creator_id` | body | string | 是 | 工单创建人ID | `123123213` |
| `work_order_id` | body | string | 是 | 工单唯一标识id | `xxxxx` |
| `open_user_id` | body | string | 是 | 抖店用户ID | `#YOUR_SECRET_KEY` |
| `relation_id_type` | body | number | 是 | 工单关联id类型，1店铺订单 2商品订单 3售后单 4商品 | `1` |
| `relation_id` | body | string | 是 | 关联单Id，如1 店铺订单ID，2 商品订单ID，3 售后单ID，4 商品ID | `4936192001894376568` |
| `work_order_type_desc` | body | string | 是 | 工单状态描述 | `换货工单` |
| `work_order_status` | body | number | 是 | 工单状态  10 待处理/ 20 处理中/30 已完结/40 已失效（已删除，飞鸽内不展示） | `10` |
| `title` | body | string | 是 | 工单标题 | `开放测试工单` |
| `event_type` | body | number | 是 | 事件类型  1 创建事件  2 更新事件 | `1` |
| `creator_id_type` | body | number | 是 | 工单创建人 账号体系 1 飞鸽账号体系 2 ISV账号体系，若为飞鸽体系，则creator_id传递飞鸽体系的身份ID，如OpenId,若为ISV账号，则需要和飞鸽协商后确定 | `1` |
| `event_time` | body | number | 是 | 事件发生时间（单位：秒) | `1654163962` |
| `scene` | body | number | 否 | 工单场景 0其他 1补发 2换货 | `0` |
| `trigger_action` | body | number | 否 | 触发操作：0无操作 1发卡片 | `0` |
| `extra_info` | body | string | 否 | 扩展数据 | `xxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/pigeon/workOrderNotify?app_key=your_appkey_here&method=pigeon.workOrderNotify&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:2008） | 请检查参数 |
| `40002` | 缺少必选参数 / 缺少必要的业务参数（sub_code: isv.missing-parameter:9002） | 请检查入参 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:9001） | 请重试 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:2006） | 请重试 |
| `40004` | 非法的参数 / 参数过期（sub_code: isv.parameter-invalid:2007） | 请重试 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:9003） | 请检查参数信息后重试 |
| `50002` | 业务处理失败 / 关联单查询失败（sub_code: isv.business-failed:2013） | 请重试 |
| `50002` | 业务处理失败 / 工单卡片发送失败（sub_code: isv.business-failed:2016） | 请检查参数信息后重试 |
| `50002` | 业务处理失败 / 工单已存在（sub_code: isv.business-failed:2018） | 请检查参数 |
| `50002` | 业务处理失败 / 工单不存在（sub_code: isv.business-failed:2005） | 请检查参数 |

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
  "sub_code": "isv.parameter-invalid:2008",
  "sub_msg": "参数非法"
}
```

## 备注
