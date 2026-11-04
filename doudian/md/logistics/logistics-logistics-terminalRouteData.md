# logistics.terminalRouteData

> 末端操作数据回传。

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.terminalRouteData` |
| 中文名 | 末端操作数据回传 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/terminalRouteData` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/2363 |
| 更新日期 | `2026-01-30` |

## 接口说明

- 文档书: 物流发货API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `track_operation` | body | string | 是 | 轨迹操作（Arrival - 入站；InStore - 在库；Departure - 出站；DepartureException - 异常出站；SignReject - 拒收；AgentSign-暂存；AwaitingDelivery-待驿站上门派送；Delivering-驿站派送中） | `Arrival` |
| `sign_by` | body | string | 否 | 签收人（SignedByMyself - 本人签收；SignedByOthers - 他人签收；PostStationSigned - 驿站代签） | `SignedByMyself` |
| `longitude` | body | string | 否 | 经度 | `11.123456` |
| `latitude` | body | string | 否 | 纬度 | `11.123456` |
| `standard` | body | string | 否 | 经纬度标准（GaoDe - 高德；BaiDu - 百度；Tencent - 腾讯；Google - 谷歌） | `GaoDe` |
| `pick_up_address` | body | object | 是 | 取件地址 | `` |
| `  └ province_code` | body | string | 否 | 省编码 | `44` |
| `  └ city_name` | body | string | 否 | 市 | `广州市` |
| `  └ street_name` | body | string | 否 | 街道 | `沙东街道` |
| `  └ city_code` | body | string | 否 | 市编码 | `440100` |
| `  └ longitude` | body | string | 否 | 经度 | `11.123456` |
| `  └ district_code` | body | string | 否 | 区编码 | `440106` |
| `  └ street_code` | body | string | 否 | 街道编码 | `440106007` |
| `  └ detail_address` | body | string | 否 | 详细地址 | `范屋街37号菜鸟驿站` |
| `  └ country_code` | body | string | 否 | 国家编码 | `CHN` |
| `  └ latitude` | body | string | 否 | 纬度 | `11.123456` |
| `  └ province_name` | body | string | 否 | 省 | `广东省` |
| `  └ district_name` | body | string | 否 | 区 | `天河区` |
| `courier_name` | body | string | 否 | 快递员姓名 | `张三` |
| `courier_tel` | body | string | 否 | 快递员电话 | `1234567711` |
| `service_type` | body | string | 是 | 服务类型（HomeDelivery - 送货上门；PostStationSelfDelivery - 驿站自提；other - 其他） | `HomeDelivery` |
| `waybill_code` | body | string | 是 | 运单号 | `12345678` |
| `express_company` | body | string | 是 | 快递公司（联调时提供枚举） | `jd` |
| `pick_code` | body | string | 否 | 取件码 | `123` |
| `pick_site_type` | body | string | 是 | 取件点类型（1 - 驿站；2 - 自提柜） | `1` |
| `pick_site_name` | body | string | 是 | 取件点名称 | `仙颐园小区熊猫快收` |
| `pick_site_code` | body | string | 是 | 取件点编码 | `服务商侧柜子/驿站编码` |
| `pick_site_phone` | body | string | 是 | 取件点联系方式 | `17812345678` |
| `operation_time` | body | string | 是 | 操作时间 | `2021-03-29 09:39:03` |
| `extend` | body | string | 否 | 拓展字段 | `-` |
| `exception_code` | body | string | 否 | 异常编码（联调时提供枚举） | `C001` |
| `exception_description` | body | string | 否 | 异常描述，服务商回传原始异常文案 | `包裹长时间未出库，滞留超时` |
| `business_end_time` | body | string | 否 | 营业结束时间，格式：xx:xx；例如：19:00 | `19:00` |
| `pickup_method` | body | string | 否 | 取件方式，枚举值：PickupCode-取件码取件；Scanning-扫码取件；WaybillNumber-运单号取件；PhoneNumber-手机号取件；VirtualNumber-虚拟号取件。（service_type=PostStationSelfDelivery-驿站自提时，需要同步用户取件的方式） | `PickupCode` |
| `pick_site_contactor` | body | string | 否 | 驿站/快递柜联系人 | `张三` |
| `business_type` | body | string | 否 | 支持的业务类型，枚举值：Collection-代收；Sending-寄件。（两个同时支持时使用英文逗号隔开）例如：Collection,Sending | `Collection,Sending` |
| `business_start_time` | body | string | 否 | 营业开始时间，格式：xx:xx；例如：09:00 | `09:00` |
| `order_scale` | body | string | 否 | 单量规模，代收点日均单量，同步区间值，格式为x-x。例如：0-100 | `0-100` |
| `brand_code` | body | string | 否 | 品牌编码（联调时提供） | `xx` |
| `cabinet_no` | body | string | 否 | 自提柜柜号 | `2` |
| `cabinet_box_no` | body | string | 否 | 自提柜格口号 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/getAreasByProvince?app_key=your_appkey_here&method=address.getAreasByProvince&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `result` | boolean | 是否成功 | `true` |
| `return_code` | string | 响应编码 | `0` |
| `message` | string | 响应描述 | `成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / rpc调用失败（sub_code: isv.business-failed:11004） | 找研发确认 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:11000） | 修改参数 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "code": "41",
        "father_code": "8",
        "level": "Province",
        "name": "河南省",
        "sub_districts": [
          {
            "code": "410500",
            "father_code": "41",
            "level": "City",
            "name": "安阳市",
            "sub_districts": [
              {
                "code": "410522",
                "father_code": "410500",
                "level": "District",
                "name": "安阳县",
                "sub_districts": [
                  {
                    "code": "410522107",
                    "father_code": "410522",
                    "level": "Street",
                    "name": "伦掌镇"
                  }
                ]
              }
            ]
          }
        ]
      }
    ]
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
  "sub_code": "isv.business-failed:11004",
  "sub_msg": "rpc调用失败"
}
```

## 备注
