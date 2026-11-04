# instantShopping.logistics.updateOrder

> 更新收件人信息 以及发件人名字联系方式信息，不支持顺丰速递更新面单信息（支持顺丰速递更新重量体积）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-waybill.instantShopping.logistics.updateOrder` |
| 中文名 | 更新收件人信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1578/7244 |
| 更新日期 | `2026-08-13` |

## 接口说明

- 文档书: 电子面单API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `store_id` | body | mixed | 是 | 门店ID | `1` |
| `receiver_info` | body | object | 否 | 收件人信息 | `` |
| `  └ contact` | body | object | 是 | 收件人联系信息 | `` |
| `    └ name` | body | string | 否 | 收件人姓名，支持密文 | `李四` |
| `    └ phone` | body | string | 否 | 收件人固话（和mobile二选一） | `1` |
| `    └ mobile` | body | string | 否 | 收件人移动电话（和phone二选一），支持密文 | `18500000034` |
| `  └ address` | body | object | 是 | 收件人地址信息 | `` |
| `    └ country_code` | body | string | 是 | 国家编码（默认CHN，目前只有国内业务） | `CHN` |
| `    └ district_name` | body | string | 是 | 区/县名称 | `海淀区` |
| `    └ street_name` | body | string | 否 | 街道名称。街道名称（street_name）和街道code（street_code），若传入时，需要一起传入。 | `丹棱街` |
| `    └ city_name` | body | string | 是 | 市名称 | `市辖区` |
| `    └ district_code` | body | string | 否 | 区code编码 | `111111` |
| `    └ city_code` | body | string | 否 | 市code编码 | `11111` |
| `    └ detail_address` | body | string | 否 | 剩余详细地址，支持密文 | `丹棱街1号` |
| `    └ province_name` | body | string | 是 | 省名称 | `北京市` |
| `    └ street_code` | body | string | 否 | 街道code编码 | `1111` |
| `    └ province_code` | body | string | 否 | 省code编码 | `11` |
| `remark` | body | string | 否 | 备注 | `1` |
| `volume` | body | string | 否 | 总体积 货物的总体积或长，宽，高 ；整数 单位cm | `1,2,3` |
| `weight` | body | mixed | 否 | 总重量 ；整数 用于与快递商有计抛信任协议的商家）单位克 | `20` |
| `extra` | body | string | 否 | 备用扩展字段 | `1` |
| `user_id` | body | mixed | 否 | 实际使用取号服务店铺user_id | `1` |
| `track_no` | body | string | 是 | 运单号 | `jt271927012` |
| `logistics_code` | body | string | 否 | 物流服务商编码 | `jtexpress` |
| `sender_info` | body | object | 否 | 发件人信息 | `` |
| `  └ contact` | body | object | 否 | 寄件人联系信息 | `` |
| `    └ mobile` | body | string | 否 | 寄件人移动电话（和phone二选一） | `18500000034` |
| `    └ name` | body | string | 否 | 寄件人姓名 | `张三` |
| `    └ phone` | body | string | 否 | 寄件人固话（和mobile二选一） | `1` |
| `items` | body | array | 否 | 商品明细信息 | `` |
| `  └ item_specs` | body | string | 否 | 商品规格 | `1` |
| `  └ item_net_weight` | body | mixed | 否 | 单件总净重量（g） | `1` |
| `  └ item_count` | body | mixed | 是 | 商品数量 | `1` |
| `  └ item_weight` | body | mixed | 否 | 单件商品重量（g) | `1` |
| `  └ item_name` | body | string | 是 | 商品名称 | `1` |
| `  └ item_volume` | body | mixed | 否 | 单件商品体积（cm3） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logistics.updateOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `track_no` | string | 运单号 | `DPK363023514956` |
| `sort_code` | string | 分拣码（三段码） | `400-W00 000` |
| `package_center_code` | string | 集包地代码 | `52` |
| `package_center_name` | string | 集包名称 | `杭州中转包1` |
| `short_address_code` | string | 大头笔编码 | `L51-00-16` |
| `short_address_code` | string | 大头笔名称 | `123456` |
| `extra_resp` | string | 扩展字段 | `{"123456"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / ERROR:该订单对应的运单号3180425096642已经有物流信息,不能进行修改（sub_code: isv.parameter-invalid:10912） | 有轨迹无法更新 |
| `40004` | 非法的参数 / 运单号不存在（sub_code: isv.parameter-invalid:10911） | 参数错误 |
| `40004` | 非法的参数 / 订单已取件，不允许变更（sub_code: isv.parameter-invalid:10902） | 无法更新 |
| `40004` | 非法的参数 / 订单已取消，不允许变更（sub_code: isv.parameter-invalid:10901） | 无法更新 |
| `40004` | 非法的参数 / 运单号不存在（sub_code: isv.parameter-invalid:10724） | 输入正确的运单号 |
| `40004` | 非法的参数 / 物流服务不支持派送（sub_code: isv.parameter-invalid:10704） | 无 |
| `40004` | 非法的参数 / 电子面单号不存在（sub_code: isv.parameter-invalid:10014） | 无 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:10000） | 无 |
| `40004` | 非法的参数 / 订单已确认（sub_code: isv.parameter-invalid:8252） | 无 |
| `40004` | 非法的参数 / 该物流商不允许更新 Weight、Volume 字段（sub_code: isv.parameter-invalid:5001） | 无 |
| `40004` | 非法的参数 / 邮政和ems接口暂时不支持除了Weight、Volume之外的字段（sub_code: isv.parameter-invalid:4006） | 无 |
| `40004` | 非法的参数 / 使用该产品需签订指定专属协议（sub_code: isv.parameter-invalid:4001） | 无 |
| `50002` | 业务处理失败 / 未获取到网点数据（sub_code: isv.business-failed:20045） | 无 |
| `50002` | 业务处理失败 / 筛单不可到:其它原因（sub_code: isv.business-failed:20019） | 无 |
| `50002` | 业务处理失败 / 账户余额不足（sub_code: isv.business-failed:10701） | 无 |
| `50002` | 业务处理失败 / 请求物流服务商超时（sub_code: isv.business-failed:4009） | 无 |
| `50002` | 业务处理失败 / 请求内部服务超时，请重试（sub_code: isv.business-failed:4007） | 无 |
| `50002` | 业务处理失败 / 11204:调用路由信息查询接口异常（sub_code: isv.business-failed:11204） | 无 |
| `50002` | 业务处理失败 / 4010:数据库查询失败（sub_code: isv.business-failed:4010） | 无 |
| `50002` | 业务处理失败 / 20043:网点获取超时,请稍后重试（sub_code: isv.business-failed:20043） | 无 |
| `50002` | 业务处理失败 / 14081:服务不可达（sub_code: isv.business-failed:14081） | 无 |
| `50002` | 业务处理失败 / 8092:到方电话或手机不合法（sub_code: isv.business-failed:8092） | 无 |
| `50002` | 业务处理失败 / 10913:末端服务不可达（sub_code: isv.business-failed:10913） | 无 |
| `50002` | 业务处理失败 / 10802:外部订单号:141209-279021\|279021_1\|43\|54订单已经揽收或上传无法修改（sub_code: isv.business-failed:10802） | 无 |
| `50002` | 业务处理失败 / 10907:60：订单状态不在可允许修改配置项内（sub_code: isv.business-failed:10907） | 无 |
| `50002` | 业务处理失败 / 817703:1:尊敬的客户，您好！因当前流向件量激增，为更好地保障您的寄件体验，暂不提供此产品寄递服务，您可选择其他产品寄递，带来不便请您理解。（sub_code: isv.business-failed:817703） | 请选择其他产品寄递 |
| `50002` | 业务处理失败 / 4008:内部数据JSON/XML格式非法   !（sub_code: isv.business-failed:4008） | 请稍后重试 |
| `50002` | 业务处理失败 / 15000:系统繁忙，请稍后重试（sub_code: isv.business-failed:15000） | 请稍后重试 |
| `50002` | 业务处理失败 / 10719:内部处理超时，请重试（sub_code: isv.business-failed:10719） | 请稍后重试 |
| `50002` | 业务处理失败 / 200101:订单已揽收或已完成，不支持修改订单（sub_code: isv.business-failed:200101） | 无 |
| `50002` | 业务处理失败 / 10903:订单号不存在（sub_code: isv.business-failed:10903） | 提工单 |
| `50002` | 业务处理失败 / 55000008:更新失败，中转入仓订单不允许更新地址，请重新取号（sub_code: isv.business-failed:55000008） | 55000008:更新失败，中转入仓订单不允许更新地址，请重新取号 |
| `50002` | 业务处理失败 / 20036:该产品的付款方式为寄付,寄转第三方可用（sub_code: isv.business-failed:20036） | 20036:该产品的付款方式为寄付,寄转第三方可用 |

## 响应示例

成功：

```json
{
  "data": {
    "extra_resp": "{\"123456\"}",
    "package_center_code": "52",
    "package_center_name": "杭州中转包1",
    "short_address_code": "123456",
    "sort_code": "400-W00 000",
    "track_no": "DPK363023514956"
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
  "sub_code": "isv.parameter-invalid:10912",
  "sub_msg": "ERROR:该订单对应的运单号3180425096642已经有物流信息,不能进行修改"
}
```

## 备注
