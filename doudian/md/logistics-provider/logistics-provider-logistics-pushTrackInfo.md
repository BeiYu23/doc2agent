# logistics.pushTrackInfo

> 异步推送面单运单信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.pushTrackInfo` |
| 中文名 | 异步推送面单运单信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushTrackInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/8373 |
| 更新日期 | `2026-06-24` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `collect_net_code` | body | string | 否 | 实际的揽收网点编码 | `123` |
| `service_list` | body | array | 否 | 增值服务列表 | `` |
| `  └ service_value` | body | string | 否 | 增值服务取值（如段码内容、JSON 等，长度上限 1MB） | `{"value":"1"}` |
| `  └ service_code` | body | string | 否 | 增值服务编码 | `SVC-XX` |
| `trans_list` | body | array | 否 | 运输方式列表 | `` |
| `  └ trans_type` | body | string | 否 | 运输方式 airfreight：空运 railway：铁路 waterway：水路 highway：公路 | `airfreight` |
| `calc_net_code` | body | string | 否 | 实际的派件网点编码 | `234343` |
| `product_type` | body | string | 否 | 产品类型 | `byte_tk` |
| `route_list` | body | array | 否 | 此运单的全局路由（揽收网点-首分拨...-末分拨-派件网点），需要传完整序列，若存在多个规划路由，传主路由 | `` |
| `  └ route_type` | body | string | 否 | 路由类型 collectNet：揽收网点 firstDistribution：首分拨 terminalDistribution：末分拨 deliveryNet：派件网点 | `collectNet` |
| `  └ route_code` | body | string | 否 | 路由编码 collectNetCode：揽收网点编码 firstDistributionCode：首分拨编码 terminalDistributionCode：末分拨编码 deliveryNetCode：派件网点编码 | `1234` |
| `track_no` | body | string | 是 | 运单号 | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/pushTrackInfo?app_key=your_appkey_here&method=logistics.pushTrackInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
