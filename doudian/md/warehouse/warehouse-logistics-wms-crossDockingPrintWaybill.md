# 越库单质检取号打印

> logistics.wms.crossDockingPrintWaybill — 越库单质检取号打印接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 越库单质检取号打印 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-logistics-wms-crossDockingPrintWaybill` |
| 接口 ID | `doudian.warehouse.logistics.wms.crossDockingPrintWaybill` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/wms/crossDockingPrintWaybill` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/6765 |
| 更新日期 | `2024-08-16` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `warehouse_code` | body | string | 是 | 仓库编码 | `01` |
| `cross_docking_order_no` | body | string | 是 | 越库单号 | `CD7397266657065943340` |
| `order_code` | body | string | 是 | 订单码 | `0755057550` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/sms/sign/delete?app_key=your_appkey_here&method=sms.sign.delete&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `cross_docking_order_no` | string | 越库单号 | `CD7397266657065943340` |
| `order_code` | string | 订单码 | `0755057550` |
| `logistics_code` | string | 快递承运商 | `shunfeng` |
| `logistics_no` | string | 快递单号 | `SF0001` |
| `print_info` | string | 面单打印信息 | `{\"cmd\":\"print\",\"requestID\":\"123458976\",\"version\":\"1.0\",\"isOpen\":false,\"task\":{\"taskID\":\"01_CD7397266657065943340_20240809143106\",\"printer\":\"\",\"preview\":false,\"config\":\"\",\"documents\":[{\"docNo\":\"CD7397266657065943340\",\"documentID\":\"41010469075\",\"copy\":1,\"contents\":[{\"params\":\"AppKey=edf6edb8-4882-46e1-a557-67c0d795fb25\\u0026ShopId=1001672549713098\\u0026TimeStamp=2024-08-09 06:31:06\\u0026V=1\\u0026Sign=6bde0c4d723de0f540563d6a18d5d70a\",\"signature\":\"YOUR_SECRET_KEY\",\"encryptedData\":\"YOUR_SECRET_KEY\",\"templateURL\":\"https://tosv.boe.byted.org/obj/logistics-YOUR_SECRET_KEY_76_130.xml\"}]}]}}` |
| `order_flow` | string | 订单流向（枚举值：consumer消费者，seller商家） | `消费者` |
| `remark` | string | 备注 | `无` |
| `warehouse_code` | string | 仓编码 | `01` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:1001） | 请重试或联系管理员 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:1004） | 请检查后重试 |
| `50002` | 业务处理失败 / 越库单单据状态不符合预期（sub_code: isv.business-failed:4004） | 请确认当前单据状态 |
| `50002` | 业务处理失败 / 取号失败（sub_code: isv.business-failed:4005） | 请重试或联系管理员 |
| `50002` | 业务处理失败 / 2010251407:越库单据状态不符合预期map[IDX_1: 待送检]（sub_code: isv.business-failed:2010251407） | 2010251407:越库单据状态不符合预期map[IDX_1: 待送检] |
| `50002` | 业务处理失败 / 2010251403:越库事务执行失败map[IDX_1:数据库异常]（sub_code: isv.business-failed:2010251403） | 2010251403:越库事务执行失败map[IDX_1:数据库异常] |
| `50002` | 业务处理失败 / 2010251104:分布式锁错误，重复请求（sub_code: isv.business-failed:2010251104） | 2010251104:分布式锁错误，重复请求 |
| `50002` | 业务处理失败 / 2030251007:InnerErrormap[]（sub_code: isv.business-failed:2030251007） | 2030251007:InnerErrormap[] |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "message": "成功"
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
  "sub_msg": "内部错误"
}
```

## 备注
