# logistics.getTraceLogisticsList

> 获取溯源物流信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.getTraceLogisticsList` |
| 中文名 | 获取溯源物流信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getTraceLogisticsList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7653 |
| 更新日期 | `2025-07-31` |

## 接口说明

- 文档书: 物流商API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_num` | body | mixed | 是 | 页码 | `1` |
| `page_size` | body | mixed | 是 | 每页数量 | `100` |
| `data_date_start` | body | string | 是 | 业务开始时间，yyyyMMddHHmmss 格式 | `20220320000000` |
| `data_date_end` | body | string | 是 | 业务结束时间，yyyyMMddHHmmss 格式 | `20220320235959` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getTraceLogisticsList?app_key=your_appkey_here&method=logistics.getTraceLogisticsList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `list` | array | 物流信息 | `` |
| `total` | mixed | 总数 | `231` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 系统内部异常（sub_code: isp.service-error:10001） | 咨询连接平台入驻人员 |

## 响应示例

成功：

```json
{
  "data": {
    "list": [
      {
        "cargo_code": "7278177207393141031",
        "city_name": "杭州市",
        "district_name": "西湖区",
        "is_gov": "Y",
        "is_gov_subsidy": "Y",
        "is_subsidy": "Y",
        "province_name": "浙江省",
        "shop_order_id": "7943843932343",
        "sign_time": "20220320010101",
        "trace_code": "SHXH534NRLYW"
      }
    ],
    "total": "231"
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
  "sub_code": "isp.service-error:10001",
  "sub_msg": "系统内部异常"
}
```

## 备注
