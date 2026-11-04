# 电子面单追加子单号场景

> logistics.appendSubOrder — 电子面单追加子单号场景；

| 元信息 | 值 |
| --- | --- |
| 中文名 | 电子面单追加子单号场景 |
| 文档地址 | `/docs/doudian/waybill/waybill-logistics-appendSubOrder` |
| 接口 ID | `doudian.waybill.logistics.appendSubOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/appendSubOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1075 |
| 更新日期 | `2021-09-14` |

## 接口说明

- 文档书: 电子面单API（版本 V2.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `track_no` | body | string | 是 | 运单号 | `1343434` |
| `logistics_code` | body | string | 是 | 物流商编码 | `shunfeng` |
| `pack_add_quantity` | body | string | 是 | 追加个数 | `1` |
| `is_return_full_sub_codes` | body | boolean | 否 | 是否返回全量的子单号 | `false` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/appendSubOrder?app_key=your_appkey_here&method=logistics.appendSubOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `track_no` | string | 运单号 | `sf2343434` |
| `pack_quantity` | number | 子母单数量 | `20` |
| `sub_waybill_codes` | string | 新追加的子单号 | `1,2,3` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 订单状态不为接货中,不允许拆单（sub_code: isv.parameter-invalid:10000） | 订单状态不为接货中,不允许拆单 |
| `50002` | 业务处理失败 / 电子面单号不存在（sub_code: isv.business-failed:10014） | 输入正确的面单号 |
| `50002` | 业务处理失败 / 订单已生成路由不能申请子单（sub_code: isv.business-failed:8168） | 订单已生成路由不能申请子单 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:400） | 参数错误 |
| `50002` | 业务处理失败 / 目标服务异常或不可达（sub_code: isv.business-failed:4007） | 目标服务异常或不可达 |
| `50002` | 业务处理失败 / 订单已取消，不允许变更（sub_code: isv.business-failed:10901） | 订单已取消，不允许变更，请检查订单状态 |
| `50002` | 业务处理失败 / 4009:请求物流服务商超时         !（sub_code: isv.business-failed:4009） | 请重试 |
| `50002` | 业务处理失败 / 4010:操作数据库异常（sub_code: isv.business-failed:4010） | 4010:操作数据库异常 |
| `50002` | 业务处理失败 / 20001:重复请求（sub_code: isv.business-failed:20001） | 20001:重复请求 |
| `50002` | 业务处理失败 / 8067:超过最大能申请子单号数量（sub_code: isv.business-failed:8067） | 8067:超过最大能申请子单号数量 |
| `50002` | 业务处理失败 / 200102:内部服务异常（sub_code: isv.business-failed:200102） | 200102:内部服务异常 |
| `50002` | 业务处理失败 / 10003:系统错误（sub_code: isv.business-failed:10003） | 10003:系统错误 |
| `50002` | 业务处理失败 / 10002:系统未知异常（sub_code: isv.business-failed:10002） | 10002:系统未知异常 |

## 响应示例

成功：

```json
{
  "data": {
    "pack_quantity": "20",
    "sub_waybill_codes": "1,2,3",
    "track_no": "sf2343434"
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
  "sub_code": "isv.parameter-invalid:10000",
  "sub_msg": "订单状态不为接货中,不允许拆单"
}
```

## 备注
