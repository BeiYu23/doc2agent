# 网点信息更新（仅用于兼容老物流网关

> power.netsiteUpdate — 网点信息更新（仅用于兼容老物流网关）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 网点信息更新（仅用于兼容老物流网关 |
| 文档地址 | `/docs/doudian/logistics/logistics-power-netsiteUpdate` |
| 接口 ID | `doudian.logistics.power.netsiteUpdate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/netsiteUpdate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1471 |
| 更新日期 | `2023-03-20` |

## 接口说明

- 文档书: 物流发货API（版本 V3.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `net_sites` | body | array | 是 | 网点信息 | `` |
| `  └ father_net_code` | body | string | 否 | 父网点编码 | `029648` |
| `  └ organization_type` | body | string | 否 | 组织类型 | `承包区` |
| `  └ company` | body | string | 是 | 物流公司 | `bytedance` |
| `  └ net_name` | body | string | 否 | 网点名称 | `八方城` |
| `  └ net_code` | body | string | 否 | 网点编码 | `200120` |
| `  └ net_area` | body | string | 否 | 网点作业面积 | `100` |
| `  └ address` | body | object | 否 | 网点地址信息 | `` |
| `    └ country_code` | body | string | 是 | 国家编码 | `CHN` |
| `    └ province_code` | body | string | 否 | 省份code，网点查询、更新、停用时code必传，其他接口可不传 | `330000` |
| `    └ province_name` | body | string | 是 | 省份，段码/路由信息相关接口该字段可传入1，表示全国 | `浙江省` |
| `    └ city_code` | body | string | 否 | 城市code，网点查询、更新、停用时code必传，其他接口可不传 | `330100` |
| `    └ city_name` | body | string | 是 | 城市，段码相关接口需要传空字符串 | `杭州市` |
| `    └ district_code` | body | string | 否 | 区县code，网点查询、更新、停用时code必传，其他接口可不传 | `330110` |
| `    └ district_name` | body | string | 是 | 区县，段码相关接口需要传空字符串 | `余杭区` |
| `    └ street_code` | body | string | 否 | 街道code | `330111` |
| `    └ street_name` | body | string | 否 | 街道，段码相关接口需要传空字符串 | `良渚街道` |
| `    └ detail_address` | body | string | 是 | 详细地址，段码相关接口需要传空字符串 | `良渚路166号` |
| `    └ address_id` | body | number | 否 | - | `0` |
| `  └ contact` | body | object | 否 | 网点联系人 | `` |
| `    └ name` | body | string | 是 | 姓名 | `张三` |
| `    └ phone` | body | string | 否 | 固定电话 | `0571-88888888` |
| `    └ mobile` | body | string | 否 | 手机号 | `13282160694` |
| `    └ email` | body | string | 否 | 邮箱 | `zhangsan@163.com` |
| `  └ facility_type` | body | string | 否 | 1-普通网点；2-分拨中心 不传默认是普通网点 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数错误（sub_code: isv.business-failed:4006） | 修正入参 |
| `50002` | 业务处理失败 / 调用物流商超时（sub_code: isv.business-failed:4009） | 重试 |
| `50002` | 业务处理失败 / 4007:202022联系人Phone或者Mobile必须有一个（sub_code: isv.business-failed:4007） | 4007:202022联系人Phone或者Mobile必须有一个 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "参数错误"
}
```

## 备注
