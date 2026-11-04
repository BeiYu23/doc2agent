# power.netsiteQuery

> 网点信息查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.power.netsiteQuery` |
| 中文名 | 网点信息查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/power/netsiteQuery` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1453 |
| 更新日期 | `2023-03-20` |

## 接口说明

- 文档书: 物流发货API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `net_codes` | body | array | 否 | 网点编码 | `["101046"]` |
| `pagination` | body | object | 否 | 翻页 | `` |
| `  └ page_num` | body | string | 否 | 第几页，默认1 | `1` |
| `  └ page_size` | body | string | 否 | 页大小，最大100 | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/power/netsiteQuery?app_key=your_appkey_here&method=power.netsiteQuery&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `net_sites` | array | 网点列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "net_sites": [
      {
        "address": {
          "address_id": "1",
          "city_code": "330100",
          "city_name": "杭州市",
          "country_code": "CHN",
          "detail_address": "良渚路166号",
          "district_code": "330110",
          "district_name": "余杭区",
          "province_code": "330000",
          "province_name": "浙江省",
          "street_code": "330111",
          "street_name": "良渚街道"
        },
        "company": "yunda",
        "contact": {
          "email": "zhangsan@163.com",
          "mobile": "18867727373",
          "name": "张三",
          "phone": "010-86383838"
        },
        "facility_type": "1",
        "father_net_code": "029648",
        "net_area": "100",
        "net_code": "200120",
        "net_name": "上海浦东新区陆家嘴公司",
        "organization_type": "承包区"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
