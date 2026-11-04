# 数据推送，发起店铺补偿任务

> openCloud.ddpAddShopTask — 数据推送，发起店铺补偿任务

| 元信息 | 值 |
| --- | --- |
| 中文名 | 数据推送，发起店铺补偿任务 |
| 文档地址 | `/docs/doudian/cloud/cloud-openCloud-ddpAddShopTask` |
| 接口 ID | `doudian.cloud.openCloud.ddpAddShopTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/ddpAddShopTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/2908 |
| 更新日期 | `2025-04-01` |

## 接口说明

- 文档书: 电商云API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `data_list` | body | array | 否 | 数据ID（仅业务单号），最多传10个 | `["123456789"]` |
| `shop_id` | body | string | 否 | 店铺ID（仅时间范围） | `77977` |
| `start_time` | body | string | 否 | 开始时间（仅时间范围） | `1735545392` |
| `end_time` | body | string | 否 | 结束时间（仅时间范围） | `1735545492` |
| `self_push_type` | body | string | 否 | 任务类型 0按更新时间 1按业务单号 | `0` |
| `biz_id` | body | string | 是 | 业务类型 1订单 2售后 3商品 | `1` |
| `range_type` | body | string | 否 | 范围类型 0自定义 1全量（仅商品） | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/outbound/create?app_key=your_appkey_here&method=yunc.wms.outbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 62208039:业务单号所属店铺未授权、未添加推送配置或相关业务推送未开启，请重新检查（sub_code: isv.business-failed:62208039） | 62208039:业务单号所属店铺未授权、未添加推送配置或相关业务推送未开启，请重新检查 |
| `50002` | 业务处理失败 / 10000000:1 min内同个店铺至多发起一次补单任务，请稍后重试（sub_code: isv.business-failed:10000000） | 10000000:1 min内同个店铺至多发起一次补单任务，请稍后重试 |
| `50002` | 业务处理失败 / 100:服务器错误.（sub_code: isv.business-failed:100） | 100:服务器错误. |
| `50002` | 业务处理失败 / 602:参数非法.（sub_code: isv.business-failed:602） | 602:参数非法. |
| `50002` | 业务处理失败 / 服务器错误（sub_code: isv.business-failed:701） | 请稍后重试 |

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
  "sub_code": "isv.business-failed:62208039",
  "sub_msg": "62208039:业务单号所属店铺未授权、未添加推送配置或相关业务推送未开启，请重新检查"
}
```

## 备注
