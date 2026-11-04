# 用于自配送场景中

> instantShopping.reportRiderLocation — 用于自配送场景中，商家向抖音回传骑手位置信息，抖音会向用户展示骑手位置

| 元信息 | 值 |
| --- | --- |
| 中文名 | 用于自配送场景中 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-instantShopping-reportRiderLocation` |
| 接口 ID | `doudian.retail-store.instantShopping.reportRiderLocation` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/4775 |
| 更新日期 | `2024-04-09` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shop_order_id` | body | string | 是 | 抖音电商shop order单id | `6917539978356459031` |
| `distribution_code` | body | string | 是 | 三方运力服务商，枚举： SF:顺丰同城 DADA:达达 FENG_NIAO:蜂鸟配送 MEI_TUAN:美团配送 SHAN_SONG:闪送 DIAN_WO_DA:点我达 UU:UU跑腿 XIN_TIAN_WENG:信天翁 SAN_LIU_WU:365跑腿 CAO_CAO:曹操跑腿 AI_PAO_TUI:爱跑腿 KUAI_PAO_ZHE:快跑者 JI_KE_KUAI_SONG:极客快送 TONG_DA:同达 SHENG_HUO_BAN_JING:生活半径 LIN_QU:临趣 QU_SONG:趣送 KUAI_FU_WU:快服务 CAI_NIAO_XIN_LIAN_MENG:菜鸟新联盟 FENG_XIAN_SHENG:风先生 LAI_DA_PEI_SONG:来答配送 HAO_JI_PAO_TUI:好急跑腿 SONG_GE_DONG_XI_PAO_TUI:送个东西跑腿 KAO_PU_SONG:靠谱送 KUAI_NAN_PAO_TUI:快男跑腿 GUO_XIAO_DI:裹小递 MERCHANT:商家自配送,使用此枚举需要提前和平台沟通 | `0` |
| `distribution_delivery_id` | body | string | 是 | 三方运单号，与发货运单号保持一致 | `SF1124756994790` |
| `rider_name` | body | string | 是 | 骑手姓名； | `王某某` |
| `rider_phone_type` | body | string | 是 | 骑手手机号类型，0是真实号，1是隐私号 | `0` |
| `rider_phone` | body | string | 是 | 骑手电话； | `12341231111` |
| `rider_longitude` | body | string | 是 | 骑手经度，高德坐标系 | `120.518486` |
| `rider_latitude` | body | string | 是 | 骑手维度，高德坐标系 | `36.894333` |
| `report_time` | body | number | 是 | 骑手上报时间戳，十位时间戳 | `1693478310` |
| `rider_coordinate_type` | body | number | 否 | 坐标系类型0 高德 1 百度 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comcrossborder/msg/push?app_key=your_appkey_here&method=crossborder.msg.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_order_id` | string | 抖音电商shop order单id | `6917539978356459031` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 查询不到对应的运力订单（sub_code: isv.business-failed:20111） | 查看传递订单是否合法 |
| `20000` | 系统错误（sub_code: isp.service-error:20100） | 系统错误 |
| `40004` | 非法的参数 / 非法的请求参数（sub_code: isv.parameter-invalid:40100） | 查看请求参数是否合理 |
| `50002` | 业务处理失败 / 503:快递发货订单不允许上报骑手位置（sub_code: isv.business-failed:503） | 503:快递发货订单不允许上报骑手位置 |
| `50002` | 业务处理失败 / 701:数据查询失败，请稍后重试（sub_code: isv.business-failed:701） | 701:数据查询失败，请稍后重试 |
| `50002` | 业务处理失败 / 99999:合约单查询失败，请稍后重试（sub_code: isv.business-failed:99999） | 99999:合约单查询失败，请稍后重试 |
| `50002` | 业务处理失败 / 702:查询数据失败，请稍后重试（sub_code: isv.business-failed:702） | 702:查询数据失败，请稍后重试 |
| `50002` | 业务处理失败 / 505:查询数据不存在，请稍后重试（sub_code: isv.business-failed:505） | 505:查询数据不存在，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "receive": "true"
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
  "sub_code": "isv.business-failed:20111",
  "sub_msg": "查询不到对应的运力订单"
}
```

## 备注
