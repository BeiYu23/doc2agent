# superm.shopOrderDispatcher

> 呼叫运力或取消

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.shopOrderDispatcher` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/shopOrderDispatcher` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2736 |
| 更新日期 | `2025-09-09` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 店铺ID | `1111409547` |
| `shop_order_id` | body | string | 是 | 订单号 | `4993668078886578045` |
| `dispatcher_type` | body | mixed | 是 | enum DispatcherType {     Call   = 1 // 呼叫运力     Cancel = 2 // 取消运力 } | `1` |
| `serial_number_list` | body | string | 否 | 序列码列表，如果包含有多个序列码，请用"_"英文下划线分割（属于数码手机类目的商品订单才需要传序列码。） | `353245234` |
| `verify_code_type` | body | mixed | 否 | 是否需要取件码(针对呼叫运力) 0否1是 | `0` |
| `insurance_amount` | body | mixed | 否 | 保价金额，单位：分 | `9900` |
| `need_receiver_code` | body | boolean | 否 | 是否需要收件码（针对呼叫运力） true：需要；false：不需要 | `true` |
| `sku_trace_info_list` | body | array | 否 | sku单的医疗溯源码信息; | `` |
| `  └ sku_order_id` | body | string | 否 | 对应sku单id | `4945222777763599988` |
| `  └ batch_and_trace_code_list` | body | array | 否 | 批次+溯源码list（设计为list是可能有多个item单） | `` |
| `    └ batch_code` | body | string | 否 | 批次code | `12345` |
| `    └ trace_code` | body | string | 否 | 溯源码code | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/superm/shopOrderDispatcher?app_key=your_appkey_here&method=superm.shopOrderDispatcher&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pickup_code` | string | 取件码 | `3301` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 店铺ID不能为空（sub_code: isv.missing-parameter:40001） | 店铺ID不能为空 |
| `40002` | 缺少必选参数 / 门店ID不能为空（sub_code: isv.missing-parameter:40002） | 门店ID不能为空 |
| `40002` | 缺少必选参数 / 订单不能为空（sub_code: isv.missing-parameter:40003） | 订单不能为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20101） | 订单查询失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20102） | 门店信息获取失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20103） | 执行单不存在,原错误码80002 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20104） | 流水号为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20200） | 履约内部rpc调用失败,原错误码503 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20201） | 调用履约呼叫运力失败 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20202） | deliverId生成失败,原错误码505 |
| `50002` | 业务处理失败 / 非小时达订单不允许使用呼叫运力（sub_code: isv.business-failed:50100） | 非小时达订单不允许使用呼叫运力 |
| `50002` | 业务处理失败 / 未开通平台运力服务，无法使用。（sub_code: isv.business-failed:50101） | 未开通平台运力服务，无法使用。 |
| `50002` | 业务处理失败 / 非本店铺订单，呼叫运力失败（sub_code: isv.business-failed:50102） | 非本店铺订单，呼叫运力失败 |
| `50002` | 业务处理失败 / 发货订单包含非本门店订单，请重试（sub_code: isv.business-failed:50103） | 发货订单包含非本门店订单，请重试 |
| `50002` | 业务处理失败 / store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID（sub_code: isv.business-failed:50104） | store_id不存在/错误，超市小时达订单发货需传入订单对应的门店ID |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50201） | 订单信息异常，sku信息为空 |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50202） | 订单信息异常，地址信息解析失败 |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50203） | 订单信息异常，地址信息解析失败 |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50204） | 订单信息异常，重量为空 |
| `50002` | 业务处理失败 / 运费获取失败，请重新获取。（sub_code: isv.business-failed:50205） | 订单信息异常，门店作业时间为空 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:50206） | 收件人信息解析失败 |
| `50002` | 业务处理失败 / 订单当前状态无法取消运力（sub_code: isv.business-failed:50301） | 订单当前状态无法取消运力 |
| `50002` | 业务处理失败 / 未开通平台运力服务，无法使用（sub_code: isv.business-failed:50111） | 未开通平台运力服务，无法使用 |
| `50002` | 业务处理失败 / 系统异常，请稍后重试（sub_code: isv.business-failed:20113） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 订单当前状态无法取消运力（sub_code: isv.business-failed:50311） | 订单当前状态无法取消运力 |
| `50002` | 业务处理失败 / 呼叫运力失败，请稍后重试（sub_code: isv.business-failed:120047） | 呼叫运力失败，请稍后重试 |
| `50002` | 业务处理失败 / 订单未成功呼叫运力，取消失败（sub_code: isv.business-failed:20211） | 订单未成功呼叫运力，取消失败 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:20111） | 订单不存在 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:20214） | 保价服务失败 |
| `20001` | 内部服务超时 / 订单已有骑手接单配送，无需重复呼叫运力（sub_code: isp.service-timeout-error:20301） | 订单已有骑手接单配送，无需重复呼叫运力 |
| `50002` | 业务处理失败 / 系统繁忙，请稍后重试（sub_code: isv.business-failed:50211） | 系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 门店未订购平台运力服务，无法呼叫运力（sub_code: isv.business-failed:60000） | 门店未订购平台运力服务，无法呼叫运力 |
| `50002` | 业务处理失败 / 60021:订单已取消，无需呼叫运力（sub_code: isv.business-failed:60021） | 订单已取消，无需呼叫运力 |
| `50002` | 业务处理失败 / 该订单暂不支持保价（sub_code: isv.business-failed:60113） | 该订单暂不支持保价 |
| `50002` | 业务处理失败 / 未开通平台运力服务（sub_code: isv.business-failed:120051） | 未开通平台运力服务 |
| `50002` | 业务处理失败 / 运力状态发生已发生变化, 请刷新后重试（sub_code: isv.business-failed:10013） | 运力状态发生已发生变化, 请刷新后重试 |
| `50002` | 业务处理失败 / 请求处理中，请稍后重试（sub_code: isv.business-failed:507） | 请求处理中，请稍后重试 |
| `50002` | 业务处理失败 / 700077:三方应用不允许对自配订单呼叫运力（sub_code: isv.business-failed:700077） | 700077:三方应用不允许对自配订单呼叫运力 |
| `50002` | 业务处理失败 / 20212:取消运力失败，请稍后重试（sub_code: isv.business-failed:20212） | 20212:取消运力失败，请稍后重试 |
| `50002` | 业务处理失败 / 500001:该门店未查询到有效的三方配送授权关系；请到配送模块-三方配送管理中完成授权后再次发单（sub_code: isv.business-failed:500001） | 500001:该门店未查询到有效的三方配送授权关系；请到配送模块-三方配送管理中完成授权后再次发单 |
| `50002` | 业务处理失败 / 20112:RPCError{PSM:[cmp.ecom.shop_info] Method:[GetShopUserListByIds] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS\|cmp.ecom.vshop:default:lf:\|cmp.ecom.shop_info:default:::\|GetShopUserListByIds\|pr（sub_code: isv.business-failed:20112） | 20112:RPCError{PSM:[cmp.ecom.shop_info] Method:[GetShopUserListByIds] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS\|cmp.ecom.vshop:default:lf:\|cmp.ecom.shop_info:default:::\|GetShopUserListByIds\|pr |
| `50002` | 业务处理失败 / 120048:取消运力失败，请稍后重试（sub_code: isv.business-failed:120048） | 120048:取消运力失败，请稍后重试 |
| `50002` | 业务处理失败 / 700002:发货订单包含非本门店订单，请重试（sub_code: isv.business-failed:700002） | 700002:发货订单包含非本门店订单，请重试 |
| `50002` | 业务处理失败 / 702:查询数据失败，请稍后重试（sub_code: isv.business-failed:702） | 702:查询数据失败，请稍后重试 |
| `50002` | 业务处理失败 / 99999:合约单查询失败，请稍后重试（sub_code: isv.business-failed:99999） | 99999:合约单查询失败，请稍后重试 |
| `50002` | 业务处理失败 / 20114:系统繁忙，请稍后重试（sub_code: isv.business-failed:20114） | 20114:系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 50216:系统繁忙，请稍后重试（sub_code: isv.business-failed:50216） | 50216:系统繁忙，请稍后重试 |
| `50002` | 业务处理失败 / 501:售后完结，订单关闭（sub_code: isv.business-failed:501） | 501:售后完结，订单关闭 |
| `50002` | 业务处理失败 / 310014:门店ID不能为空（sub_code: isv.business-failed:310014） | 310014:门店ID不能为空 |
| `50002` | 业务处理失败 / 40100:请输入正确的运力操作（sub_code: isv.business-failed:40100） | 40100:请输入正确的运力操作 |

## 响应示例

成功：

```json
{
  "data": {
    "pickup_code": "3301"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:40001",
  "sub_msg": "店铺ID不能为空"
}
```

## 备注
