# 获取备案基础信息

> crossBorder.GetProductRecordBasicOptions — 获取备案基础信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取备案基础信息 |
| 文档地址 | `/docs/doudian/cross-border/cross-border-crossBorder-GetProductRecordBasicOptions` |
| 接口 ID | `doudian.cross-border.crossBorder.GetProductRecordBasicOptions` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/crossBorder/GetProductRecordBasicOptions` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/53/6320 |
| 更新日期 | `2024-03-26` |

## 接口说明

- 文档书: 跨境API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `extra` | body | string | 否 | 额外信息 | `{"xx": "xxx"}` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/crossBorder/GetProductRecordBasicOptions?app_key=your_appkey_here&method=crossBorder.GetProductRecordBasicOptions&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | 返回码 | `0` |
| `msg` | string | 返回结果描述 | `-` |
| `customs_sp_warehouse_list` | array | 清关口岸-服务商仓信息 | `` |
| `extra` | string | 额外信息 | `{"示例":""}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 内部系统异常（sub_code: isp.service-error:10000） | 重试，多次失败联系平台处理 |
| `60000` | 触发限流，请稍后重试 / 达到qps上限，触发限流（sub_code: isp.traffic-limited:10002） | 重试，并调整流量，控制QPS符合平台要求 |
| `40004` | 非法的参数 / 参数异常（sub_code: isv.parameter-invalid:20000） | 请检查参数后重试 |
| `50002` | 业务处理失败 / 业务处理异常（sub_code: isv.business-failed:30000） | 结合返回信息处理，有疑问联系平台处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "customs_sp_warehouse_list": [
      {
        "customs_code": "ZZJC",
        "customs_name": "杭州下沙",
        "sp_warehouse_list": [
          {
            "sp_code": "0127",
            "sp_name": "北京字节跳动科技有限公司",
            "warehouse_list": [
              {
                "clear_type_list": "[0, 1]",
                "warehouse_code": "LYYBBC",
                "warehouse_mode": "1",
                "warehouse_name": "懒洋洋仓"
              }
            ]
          }
        ]
      }
    ],
    "extra": {},
    "msg": "-"
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
  "sub_code": "isp.service-error:10000",
  "sub_msg": "内部系统异常"
}
```

## 备注
