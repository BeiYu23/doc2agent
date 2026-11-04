# address.getProvince

> 获取四级地址全量省份信息
物流发货获取省份列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.address.getProvince` |
| 中文名 | 获取四级地址全量省份信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/address/getProvince` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/1848 |
| 更新日期 | `2022-08-08` |

## 接口说明

- 文档书: 物流发货API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/address/getProvince?app_key=your_appkey_here&method=address.getProvince&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 500:RPCError{PSM:[ecom.trade.address] Method:[GetProvinceList] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS\|cmp.ecom.address:default:hl:\|ecom.trade.address:default::\|GetProvinceList\|prod\| reason=（sub_code: isv.business-failed:500） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "province": "河南省",
        "province_id": "41"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:500",
  "sub_msg": "500:RPCError{PSM:[ecom.trade.address] Method:[GetProvinceList] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS|cmp.ecom.address:default:hl:|ecom.trade.address:default::|GetProvinceList|prod| reason="
}
```

## 备注
