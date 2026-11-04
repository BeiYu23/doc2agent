# supplyChain.address.list

> 供应商地址查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.address.list` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/supplyChain/address/list` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6473 |
| 更新日期 | `2024-04-26` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每一页的条数，最大100 | `100` |
| `address_type` | body | mixed | 是 | 地址信息类型 1:发货地址 2:收货地址 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/supplyChain/address/list?app_key=your_appkey_here&method=supplyChain.address.list&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务错误（sub_code: isp.service-error:1000） | 请稍后重试 |
| `50002` | 业务处理失败 / 查询地址失败（sub_code: isv.business-failed:7004） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "list": [
        {
          "address_detail": "xx路xx号xx小区xx室",
          "address_info_id": "1",
          "address_type": "1",
          "area_code": "3301100000000",
          "area_name": "余杭区",
          "city_code": "330100",
          "city_name": "杭州市",
          "contact_mobile": "13612345678",
          "contact_name": "张三",
          "is_default": "1",
          "province_code": "33",
          "province_name": "浙江省",
          "street_code": "3301100120000",
          "street_name": "仓前街道"
        }
      ],
      "page": "1",
      "page_size": "100",
      "total": "1000"
    }
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
  "sub_code": "isp.service-error:1000",
  "sub_msg": "服务错误"
}
```

## 备注
