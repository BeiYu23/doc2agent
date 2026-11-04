# logistics.pushOnlineServiceConfig

> 物流商推送面单服务的配置

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.pushOnlineServiceConfig` |
| 中文名 | 物流商推送面单服务的配置 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/pushOnlineServiceConfig` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/6744 |
| 更新日期 | `2024-08-02` |

## 接口说明

- 文档书: 电子面单API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_type` | body | string | 否 | 服务类型。0-增值服务；1-产品类型 | `1` |
| `desc` | body | string | 否 | 服务描述 | `该服务提供了更快更优的派送体验` |
| `is_auto_open` | body | mixed | 否 | 是否自动开通。0-否；1-是 | `1` |
| `operator_name` | body | string | 否 | 操作人名称 | `李四` |
| `operator_id` | body | string | 否 | 操作人ID | `123` |
| `name` | body | string | 否 | 服务名称（也是面单打印的名称） | `航空件` |
| `code` | body | string | 否 | 服务code | `XXX` |
| `route_list` | body | array | 否 | 线路限制 | `` |
| `  └ send_address` | body | object | 否 | 寄件地址 | `` |
| `    └ district_name` | body | string | 否 | 地区名称 | `区县` |
| `    └ province_name` | body | string | 否 | 省名称 | `省份` |
| `    └ street_name` | body | string | 否 | 街道名称 | `街道` |
| `    └ city_name` | body | string | 否 | 城市名称 | `城市` |
| `  └ rece_address` | body | object | 否 | 收件地址 | `` |
| `    └ street_name` | body | string | 否 | 街道名称 | `街道` |
| `    └ province_name` | body | string | 否 | 省名称 | `省份` |
| `    └ city_name` | body | string | 否 | 城市名称 | `城市` |
| `    └ district_name` | body | string | 否 | 区县名称 | `区县` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/pushOnlineServiceConfig?app_key=your_appkey_here&method=logistics.pushOnlineServiceConfig&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
