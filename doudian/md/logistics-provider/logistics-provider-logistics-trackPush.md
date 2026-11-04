# logistics.trackPush

> 快递模式轨迹推送

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.trackPush` |
| 中文名 | 快递模式轨迹推送 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/trackPush` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2643 |
| 更新日期 | `2025-08-22` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cur_time` | body | string | 是 | 推送时间 | `2022-04-28 10:17:51` |
| `company` | body | string | 是 | 快递公司编码 | `powertestexpress` |
| `trace_msgs` | body | array | 是 | 消息列表 | `` |
| `  └ track_no` | body | string | 是 | 运单号 | `SF0001` |
| `  └ traces` | body | array | 是 | 运单对应的轨迹列表 | `` |
| `    └ trace_type` | body | string | 是 | 轨迹的一级类型 | `ORDER` |
| `    └ trace_sub_type` | body | string | 是 | 轨迹的二级类型 | `ORDER_RECEIVED` |
| `    └ op_time` | body | string | 是 | 当前轨迹的操作时间 | `2020-09-09 12:04:05` |
| `    └ content` | body | string | 是 | 轨迹文案 | `西湖网点已揽收` |
| `    └ current_address` | body | object | 否 | 操作网点地址 | `` |
| `      └ province` | body | string | 否 | 省份名称 | `浙江省` |
| `      └ province_code` | body | string | 否 | 省份编码 | `33` |
| `      └ city` | body | string | 否 | 城市名称 | `杭州市` |
| `      └ city_code` | body | string | 否 | 城市编码 | `3306` |
| `      └ town` | body | string | 否 | 区县名称 | `西湖区` |
| `      └ town_code` | body | string | 否 | 区县编码 | `330666` |
| `      └ street` | body | string | 否 | 街道名称 | `西湖街道` |
| `      └ street_code` | body | string | 否 | 街道编码 | `33066666` |
| `      └ detail` | body | string | 否 | 详细地址 | `西湖` |
| `    └ next_address` | body | object | 否 | 发件轨迹等发往下一网点的地址 | `` |
| `      └ province` | body | string | 否 | 省份名称 | `浙江省` |
| `      └ province_code` | body | string | 否 | 省份编码 | `33` |
| `      └ city` | body | string | 否 | 城市名称 | `杭州市` |
| `      └ city_code` | body | string | 否 | 城市编码 | `3306` |
| `      └ town` | body | string | 否 | 区县名称 | `西湖区` |
| `      └ town_code` | body | string | 否 | 区县编码 | `330666` |
| `      └ street` | body | string | 否 | 街道名称 | `西湖街道` |
| `      └ street_code` | body | string | 否 | 街道编码 | `33066666` |
| `      └ detail` | body | string | 否 | 详细地址 | `西湖` |
| `    └ reason` | body | string | 否 | 原因 | `原因` |
| `    └ city` | body | string | 否 | 网点所在城市 | `杭州市` |
| `    └ site_name` | body | string | 否 | 网点名称 | `西湖一区网点` |
| `    └ site_code` | body | string | 否 | 网点编码 | `00001` |
| `    └ operator_name` | body | string | 否 | 操作员姓名 | `小张` |
| `    └ operator_phone` | body | string | 否 | 操作员电话 | `17812345678` |
| `    └ facility_type` | body | string | 否 | 网点类型 | `1` |
| `    └ next_site_code` | body | string | 否 | 下一网点编码 | `00002` |
| `    └ exception_code` | body | string | 否 | 异常编码 | `1000001` |
| `    └ description` | body | string | 否 | 异常原因描述 | `道路原因` |
| `    └ new_track_no` | body | string | 否 | 换单单号 | `SF00002` |
| `    └ new_company` | body | string | 否 | 换单快递公司编码 | `powertestexpress` |
| `    └ time` | body | string | 否 | 预约时间 | `2022-04-28 10:17:54` |
| `    └ third_sort_code` | body | string | 否 | 三段码 | `x` |
| `    └ is_not_learning` | body | boolean | 否 | 无需学习标记（布尔类型） | `false` |
| `    └ courier_id` | body | string | 否 | 派件人ID | `x` |
| `    └ third_party_company` | body | string | 否 | 代派公司编码 | `shunfeng` |
| `    └ address` | body | string | 否 | 提货地址/驿站地址 | `小区门口右转第一家驿站` |
| `    └ pick_code` | body | string | 否 | 提货码 | `15-2-0` |
| `    └ station_name` | body | string | 否 | 驿站名称 | `xx驿站` |
| `    └ station_phone` | body | string | 否 | 驿站电话 | `17712345678` |
| `    └ cabinet_name` | body | string | 否 | 自提柜名称 | `xx小区11幢旁自提柜` |
| `    └ reason_type` | body | string | 否 | 原因类型编码，不同二级事件下传不同的类型 | `01` |
| `    └ new_address` | body | object | 否 | 改地址新地址 | `` |
| `      └ province` | body | string | 否 | 省份名称 | `浙江省` |
| `      └ province_code` | body | string | 否 | 省份编码 | `33` |
| `      └ city` | body | string | 否 | 城市名称 | `杭州市` |
| `      └ city_code` | body | string | 否 | 城市编码 | `3306` |
| `      └ town` | body | string | 否 | 区县名称 | `西湖区` |
| `      └ town_code` | body | string | 否 | 区县编码 | `330666` |
| `      └ street` | body | string | 否 | 街道名称 | `西湖街道` |
| `      └ street_code` | body | string | 否 | 街道编码 | `33066666` |
| `      └ detail` | body | string | 否 | 详细地址 | `西湖` |
| `    └ new_receiver` | body | object | 否 | 改地址新收件人 | `` |
| `      └ name` | body | string | 否 | 改地址新收件人姓名 | `小李` |
| `      └ mobile` | body | string | 否 | 改地址新收件人电话 | `17712345678` |
| `    └ signer_name` | body | string | 否 | 签收人 | `本人` |
| `    └ operator_type` | body | string | 否 | 操作类型 | `移库` |
| `    └ delivery_type` | body | string | 否 | 派件方式 | `驿站上门` |
| `    └ scrap_type` | body | string | 否 | 报废类型 | `遗失` |
| `    └ take_type` | body | string | 否 | 取出方式 | `CourierTake` |
| `    └ station_type` | body | string | 否 | 驿站类型 | `PostStation` |
| `    └ trans_type` | body | string | 否 | 运输方式 | `Airfreight` |
| `    └ location` | body | object | 否 | 定位信息 | `` |
| `      └ longitude` | body | string | 否 | 经度 | `32.222222` |
| `      └ latitude` | body | string | 否 | 纬度 | `13.111111` |
| `      └ standard` | body | string | 否 | 坐标系 | `GaoDe` |
| `    └ city_type` | body | string | 否 | 城市属性 | `origin` |
| `    └ pick_time` | body | string | 否 | 自提时间 | `2022-04-28 10:17:54` |
| `    └ service_type` | body | string | 否 | test | `test` |
| `    └ photo_message` | body | array | 否 | 签收拍照 | `["url"]` |
| `    └ installation_worker` | body | string | 否 | 送装师傅名称 | `test` |
| `    └ time_info` | body | array | 否 | 时效信息列表 | `` |
| `      └ time_type` | body | string | 否 | 时效类型 | `1: 预计送达时效 2: 预计中转/网点发出时间 3: 预计到达下一站时间 4: 预约派送时间 5: 预约揽收时间` |
| `      └ date` | body | string | 否 | 时效日期 | `2024-07-17` |
| `      └ time` | body | string | 否 | 时效时间 | `14:22:00` |
| `      └ is_display` | body | boolean | 否 | 物流商是否在轨迹文案里展示了这个时间 | `true` |
| `    └ phone_contact` | body | object | 否 | 电联信息 | `` |
| `      └ contact_time` | body | string | 否 | 拨打时间 | `2024-07-17 10:10:55` |
| `      └ is_phone_contacted` | body | boolean | 否 | 是否电联 | `false` |
| `      └ is_connected` | body | boolean | 否 | 是否接通 | `false` |
| `      └ ring_duration` | body | mixed | 否 | 振铃时长 | `0` |
| `      └ call_duration` | body | mixed | 否 | 通话时长 | `0` |
| `    └ installation_completion_picture` | body | string | 否 | 安装服务完成截图 | `test` |
| `    └ installation_phone` | body | string | 否 | 送装师傅电话 | `test` |
| `    └ voice_message` | body | string | 否 | 语音留言 | `录音url` |
| `    └ installation_completion_time` | body | string | 否 | 安装服务完成时间 | `2024-07-17 10:10:55` |
| `    └ partner_code` | body | string | 否 | 第三方服务提供商编码 | `第三方服务提供商编码` |
| `    └ event_originator` | body | string | 否 | 事件发起方 | `事件发起方` |
| `    └ partner_name` | body | string | 否 | 第三方服务提供商名称 | `第三方服务提供商名称` |
| `    └ station_code` | body | string | 否 | 驿站编码 | `驿站编码` |
| `    └ cabinet_code` | body | string | 否 | 自提柜编码 | `自提柜编码` |
| `    └ cabinet_contactor` | body | string | 否 | 自提柜联系人 | `张三` |
| `    └ pick_address` | body | object | 否 | 驿站/自提柜地址 | `` |
| `      └ city` | body | string | 否 | 城市名称 | `杭州市` |
| `      └ town` | body | string | 否 | 区县名称 | `西湖区` |
| `      └ town_code` | body | string | 否 | 区县编码 | `330666` |
| `      └ street` | body | string | 否 | 街道名称 | `西湖街道` |
| `      └ detail` | body | string | 否 | 详细地址 | `西湖` |
| `      └ province` | body | string | 否 | 省份名称 | `浙江省` |
| `      └ city_code` | body | string | 否 | 城市编码 | `3306` |
| `      └ street_code` | body | string | 否 | 街道编码 | `33066666` |
| `      └ province_code` | body | string | 否 | 省份编码 | `33` |
| `    └ station_contactor` | body | string | 否 | 驿站联系人 | `张三` |
| `    └ pick_location` | body | object | 否 | 驿站/自提柜经纬度 | `` |
| `      └ longitude` | body | string | 否 | 经度 | `32.222222` |
| `      └ latitude` | body | string | 否 | 纬度 | `13.111111` |
| `      └ standard` | body | string | 否 | 轨迹的经纬度标准 | `GaoDe` |
| `    └ cabinet_phone` | body | string | 否 | 自提柜联系电话 | `17712345678` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/trackPush?app_key=your_appkey_here&method=logistics.trackPush&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 轨迹参数解析错误（sub_code: isv.parameter-invalid:-20005） | 检查请求入参 |

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
  "sub_code": "isv.parameter-invalid:-20005",
  "sub_msg": "轨迹参数解析错误"
}
```

## 备注
