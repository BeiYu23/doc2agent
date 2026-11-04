# 同城零售运力呼叫和运力取消

> yunc.callAndCancelTransportCapability — 同城零售运力呼叫和运力取消接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 同城零售运力呼叫和运力取消 |
| 文档地址 | `/docs/doudian/warehouse/warehouse-yunc-callAndCancelTransportCapability` |
| 接口 ID | `doudian.warehouse.yunc.callAndCancelTransportCapability` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/yunc/callAndCancelTransportCapability` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/3581 |
| 更新日期 | `2023-04-21` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | string | 是 | 门店ID（运力服务商侧的门店ID） | `11111` |
| `platform_order_no` | body | string | 是 | 订单ID（店铺单）抖音电商平台交易父订单号（如果合单，取合单的其一即可） | `6917531973167941080` |
| `order_details` | body | array | 是 | 合单订单需要告知抖音电商交易父子订单号列表 | `` |
| `  └ platform_order_no` | body | string | 是 | 抖音电商平台交易父订单号 | `6917531973167941080` |
| `  └ subplatform_order_no` | body | string | 是 | 抖音电商平台交易子订单号 | `6917531973167941080` |
| `out_order_no` | body | string | 是 | ERP单号 | `xzstest20230417` |
| `sender_info` | body | object | 否 | 发件人信息（条件必填，呼叫运力时必填！） | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ province` | body | string | 否 | 省份名称（必传） | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `002` |
| `  └ city` | body | string | 否 | 城市名称（必传） | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `003` |
| `  └ district` | body | string | 否 | 地区名称（必传） | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `004` |
| `  └ street` | body | string | 否 | 街道名称 | `闲林街道` |
| `  └ detail` | body | string | 否 | 详细地址（必传） | `西溪八方城` |
| `  └ name` | body | string | 否 | 姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 联系方式（mobile/tel_phone 其一必传） | `15677711111` |
| `  └ tel_phone` | body | string | 否 | 固定电话（mobile/tel_phone 其一必传） | `15677711111` |
| `  └ oaids` | body | string | 否 | 地址id | `地址id` |
| `receiver_info` | body | object | 否 | 收件人信息（条件必填，呼叫运力时必填！） | `` |
| `  └ province_code` | body | string | 否 | 省份编码 | `001` |
| `  └ province` | body | string | 否 | 省份名称（必传） | `安徽省` |
| `  └ city_code` | body | string | 否 | 城市编码 | `002` |
| `  └ city` | body | string | 否 | 城市名称（必传） | `合肥市` |
| `  └ district_code` | body | string | 否 | 地区编码 | `003` |
| `  └ district` | body | string | 否 | 地区名称（必传） | `蜀山区` |
| `  └ street_code` | body | string | 否 | 街道编码 | `004` |
| `  └ street` | body | string | 否 | 街道名称 | `闲林街道` |
| `  └ detail` | body | string | 否 | 详细地址（必传） | `西溪八方城` |
| `  └ name` | body | string | 否 | 姓名 | `张三` |
| `  └ mobile` | body | string | 否 | 联系方式（mobile/tel_phone 其一必传） | `15677711111` |
| `  └ tel_phone` | body | string | 否 | 固定电话（mobile/tel_phone 其一必传） | `15677711111` |
| `  └ oaids` | body | string | 否 | 地址id | `地址id` |
| `service_provider` | body | string | 是 | 呼单运力服务商品牌（shenzhenshishun=顺丰同城，dajiangwangluo=达达） | `shenzhenshishun` |
| `dispatcher_type` | body | string | 是 | 1 = 呼叫运力，2 = 取消运力 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/outbound/cancel?app_key=your_appkey_here&method=yunc.wms.outbound.cancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20001` | 内部服务超时 / 1103:内部服务超时，请重试（sub_code: isp.service-timeout-error:1103） | 请重试！ |
| `50002` | 业务处理失败 / -200001:运力平台下单错误:[不支持该收货地址]（sub_code: isv.business-failed:-200001） | -200001:运力平台下单错误:[不支持该收货地址] |
| `50002` | 业务处理失败 / 120003:虚拟号生成失败，被风控拦截（sub_code: isv.business-failed:120003） | 120003:虚拟号生成失败，被风控拦截 |
| `50002` | 业务处理失败 / 161001:Redis获取锁失败,请重试（sub_code: isv.business-failed:161001） | 161001:Redis获取锁失败,请重试 |
| `50002` | 业务处理失败 / 110022:仓id与运力服务商校验失败（sub_code: isv.business-failed:110022） | 110022:仓id与运力服务商校验失败 |
| `50002` | 业务处理失败 / -500:-500（sub_code: isv.business-failed:-500） | -500:-500 |
| `50002` | 业务处理失败 / 110023:存在未取消的lo单号（sub_code: isv.business-failed:110023） | 110023:存在未取消的lo单号 |
| `50002` | 业务处理失败 / 110024:已取消状态不许重新取号（sub_code: isv.business-failed:110024） | 110024:已取消状态不许重新取号 |
| `50002` | 业务处理失败 / 1279:原单已取消，若继续发货请更换单号后推送云仓（sub_code: isv.business-failed:1279） | 1279:原单已取消，若继续发货请更换单号后推送云仓 |
| `50002` | 业务处理失败 / 1280:订单已完结，请勿重推推单！（sub_code: isv.business-failed:1280） | 1280:订单已完结，请勿重推推单！ |
| `50002` | 业务处理失败 / 11005:ID生成失败（sub_code: isv.business-failed:11005） | 11005:ID生成失败 |
| `50002` | 业务处理失败 / 11203:状态不允许取消（sub_code: isv.business-failed:11203） | 11203:状态不允许取消 |
| `50002` | 业务处理失败 / 11102:写操作数据库更新异常（sub_code: isv.business-failed:11102） | 11102:写操作数据库更新异常 |
| `50002` | 业务处理失败 / 16003:Redis异常（sub_code: isv.business-failed:16003） | 16003:Redis异常 |
| `50002` | 业务处理失败 / 120025:查询商家订单标签失败（sub_code: isv.business-failed:120025） | 120025:查询商家订单标签失败 |

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
  "code": 20001,
  "msg": "内部服务超时",
  "sub_code": "isp.service-timeout-error:1103",
  "sub_msg": "1103:内部服务超时，请重试"
}
```

## 备注
