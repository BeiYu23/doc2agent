# logistics.updateTerminalOrder

> 末端订单状态推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.updateTerminalOrder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/updateTerminalOrder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2016 |
| 更新日期 | `2026-09-16` |

## 接口说明

- 文档书: 物流发货API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `bizType` | body | string | 否 | 推送状态标识 | `CABINET_STATUS` |
| `cabinetNum` | body | string | 否 | 快递柜编码 | `12` |
| `cabinetName` | body | string | 否 | 快递柜名称 | `12` |
| `cabinetLongitude` | body | string | 否 | 快递柜经度 | `1234` |
| `cabinetLatitude` | body | string | 否 | 快递柜纬度 | `1234` |
| `cabinetAddress` | body | object | 否 | 快递柜地址 | `` |
| `  └ cityCode` | body | string | 否 | 市编码 | `220000` |
| `  └ provinceName` | body | string | 否 | 省名称 | `浙江省` |
| `  └ districtCode` | body | string | 否 | 区编码 | `220001` |
| `  └ countryCode` | body | string | 否 | 国家编码 | `cn` |
| `  └ streetCode` | body | string | 否 | 街道编码 | `220011` |
| `  └ streetName` | body | string | 否 | 街道名称 | `仓前街道` |
| `  └ cityName` | body | string | 否 | 市名称 | `杭州市` |
| `  └ districtName` | body | string | 否 | 区名称 | `余杭区` |
| `  └ detailAddress` | body | string | 否 | 详细地址 | `爱力中心` |
| `  └ provinceCode` | body | string | 否 | 省编码 | `22` |
| `orderId` | body | string | 否 | 订单号 | `lfo12345678` |
| `operationTime` | body | string | 否 | 操作时间 | `2022-06-15 11:20:32` |
| `terminalInfo` | body | object | 否 | 订单信息 | `` |
| `  └ waybillCode` | body | string | 否 | 运单号 | `1234567` |
| `  └ operatorPhone` | body | string | 否 | 取件人号码 | `1234567` |
| `  └ operatorName` | body | string | 否 | 取件人姓名 | `李四` |
| `  └ express` | body | string | 否 | 物流商编码 | `jd` |
| `  └ courierTel` | body | string | 否 | 快递员号码 | `112345656` |
| `  └ weightInfo` | body | object | 否 | 核重核价信息 | `` |
| `    └ chargedType` | body | mixed | 否 | 计费类型 | `1` |
| `    └ packageFee` | body | mixed | 否 | 包装费用 | `12` |
| `    └ bulkyWeight` | body | mixed | 否 | 泡重 | `13` |
| `    └ certificate_photos` | body | array | 否 | 核重核价凭证图片url列表 | `["https://xxx.jpg","https://xxx2.jepg"]` |
| `    └ site` | body | string | 否 | 站点 | `xx仓库` |
| `    └ chargedWeight` | body | mixed | 否 | 计费重量 | `12` |
| `    └ is_master_and_child` | body | boolean | 否 | 是否子母单 | `false` |
| `    └ bulkyRatio` | body | mixed | 否 | 泡重比 | `13` |
| `    └ child_package_volume_list` | body | array | 否 | 子单体积数据 | `` |
| `      └ width` | body | mixed | 否 | 包裹宽度 | `100` |
| `      └ length` | body | mixed | 否 | 包裹长度 | `100` |
| `      └ height` | body | mixed | 否 | 包裹高度 | `100` |
| `    └ insuredFee` | body | mixed | 否 | 保价费用 | `12` |
| `    └ traceType` | body | string | 否 | 物流节点 | `TRANS` |
| `    └ width` | body | string | 否 | 宽度 单位cm | `13.0` |
| `    └ sumFee` | body | mixed | 否 | 总费用 | `12` |
| `    └ actualWeight` | body | mixed | 否 | 实际重量 | `12` |
| `    └ height` | body | string | 否 | 高度 单位cm | `13.0` |
| `    └ length` | body | string | 否 | 长度 单位cm | `13.0` |
| `  └ courierName` | body | string | 否 | 快递员姓名 | `张三` |
| `requestId` | body | string | 否 | 请求唯一标识 | `123456789` |
| `weightTimes` | body | mixed | 否 | 核重核价次数 | `1` |
| `transferOrderResult` | body | boolean | 否 | 转单结果 | `true` |
| `transferErrCode` | body | string | 否 | 转单失败编码 | `10823` |
| `transferErrReason` | body | string | 否 | 转单失败原因 | `寄方电话加入防骚扰` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/updateTerminalOrder?app_key=your_appkey_here&method=logistics.updateTerminalOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `isWeightException` | boolean | 是否重量异常 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 修改参数 |
| `50002` | 业务处理失败 / bizType非法（sub_code: isv.business-failed:13001） | 修改bizType参数 |
| `50002` | 业务处理失败 / 订单不存在（sub_code: isv.business-failed:11005） | 修改订单号 |
| `50002` | 业务处理失败 / 状态机初始化失败（sub_code: isv.business-failed:12001） | 联系技术 |
| `50002` | 业务处理失败 / 当前状态不允许更新（sub_code: isv.business-failed:12002） | 联系技术 |
| `50002` | 业务处理失败 / mq异常（sub_code: isv.business-failed:11002） | 重试 |
| `50002` | 业务处理失败 / 数据库异常（sub_code: isv.business-failed:11001） | 重试 |
| `50002` | 业务处理失败 / 数据库并发异常（sub_code: isv.business-failed:11017） | 联系技术 |
| `50002` | 业务处理失败 / 订单已取消（sub_code: isv.business-failed:13003） | 联系技术 |
| `50002` | 业务处理失败 / 重量异常（sub_code: isv.business-failed:11019） | 二次核重核价 |
| `50002` | 业务处理失败 / 内部系统异常（sub_code: isv.business-failed:11003） | 联系技术 |
| `50002` | 业务处理失败 / 可重试错误码（sub_code: isv.business-failed:10002） | 重试 |

## 响应示例

成功：

```json
{
  "data": {
    "isWeightException": "true"
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
  "sub_code": "isv.parameter-invalid:11000",
  "sub_msg": "参数错误"
}
```

## 备注
