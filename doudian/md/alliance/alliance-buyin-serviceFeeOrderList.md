# buyin.serviceFeeOrderList

> 可查询MCN机构绑定达人周期内百应商达合作订单（包含纯佣及坑位费订单）数据情况

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.serviceFeeOrderList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/serviceFeeOrderList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2895 |
| 更新日期 | `2023-05-30` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `start_time` | body | string | 否 | 订单更新开始时间 | `2006-01-02 15:04:05` |
| `end_time` | body | string | 否 | 订单更新结束时间 | `2006-01-02 15:04:05` |
| `kol_buyin_id` | body | string | 是 | 达人百应ID | `798984394090430` |
| `page` | body | number | 是 | 页码，起始1 | `1` |
| `page_size` | body | number | 是 | 分页大小，20 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comyunc/wms/inbound/create?app_key=your_appkey_here&method=yunc.wms.inbound.create&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `order_list` | array | 订单列表 | `` |
| `total` | number | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 无效size（sub_code: isv.parameter-invalid:1031） | 无效size |
| `40004` | 非法的参数 / 无效开始时间（sub_code: isv.parameter-invalid:1034） | 无效开始时间 |
| `40004` | 非法的参数 / 无效结束时间（sub_code: isv.parameter-invalid:1035） | 无效结束时间 |
| `40004` | 非法的参数 / 无效用户（sub_code: isv.parameter-invalid:4157） | 无效用户 |
| `40004` | 非法的参数 / 订单类型无效（sub_code: isv.parameter-invalid:263） | 订单类型无效 |
| `50002` | 业务处理失败 / 达人不属于机构（sub_code: isv.business-failed:4510） | 达人不属于机构 |
| `50002` | 业务处理失败 / 需【电商MCN机构】角色授权后访问（sub_code: isv.business-failed:4196） | 需【电商MCN机构】角色授权后访问 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
