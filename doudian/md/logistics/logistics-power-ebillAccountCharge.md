# power.ebillAccountCharge

> 面单余额充值/撤销（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.ebillAccountCharge` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/ebillAccountCharge` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1489 |
| 更新日期 | `2021-11-24` |

## 接口说明

- 文档书: 物流发货API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `unique_code` | body | string | 是 | 唯一编码 | `test26` |
| `shop_id_compatible` | body | string | 是 | 商家ID | `95250` |
| `net_code` | body | string | 是 | 网点编码 | `3025100` |
| `quantity` | body | string | 是 | 充值数量 若为正数，代表充值； 若为负数，代表撤销； 若为0，则为非法 | `10` |
| `product_type` | body | string | 否 | 具有独立库存时，必填 产品类型编码 | `000000` |
| `service_code` | body | string | 否 | 具有独立库存时，必填 增值服务编码 | `000000` |
| `recharge_type` | body | string | 是 | 充值类型（1-业务人工充值/撤回、2-系统自动回收/返还，主要用于1.0切换到2.0版本后，1.0中取走的单号符合回收要求但未给商家返还单量的场景） | `1` |
| `operator_id` | body | string | 是 | 操作员ID | `0000` |
| `operator_name` | body | string | 是 | 操作员名称 | `test011203` |
| `op_timestamp` | body | number | 是 | 操作时间戳（毫秒级） | `1629278247813` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/ebillAccountCharge?app_key=your_appkey_here&method=power.ebillAccountCharge&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `reslut` | string | 返回结果 | `空` |
| `msg` | string | 返回消息 | `空` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 14025:撤销数量不能大于库存数量（sub_code: isv.business-failed:14025） | 请检查请求数量 |
| `50002` | 业务处理失败 / 14023:电子面单账户不存在, 请申请开通（sub_code: isv.business-failed:14023） | 请先申请电子面单账户 |
| `50002` | 业务处理失败 / 11201:uniqueCode重复（sub_code: isv.business-failed:11201） | 请检查uniqueCode |
| `50002` | 业务处理失败 / 14039:超过扣减库存最大重试次数（sub_code: isv.business-failed:14039） | 请检查库存数 |
| `50002` | 业务处理失败 / 14037:Redis操作异常（sub_code: isv.business-failed:14037） | 请重试 |
| `50002` | 业务处理失败 / 4006:充值数量不能为0（sub_code: isv.business-failed:4006） | 4006:充值数量不能为0 |

## 响应示例

成功：

```json
{
  "data": {
    "msg": "空",
    "reslut": "空"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:14025",
  "sub_msg": "14025:撤销数量不能大于库存数量"
}
```

## 备注
