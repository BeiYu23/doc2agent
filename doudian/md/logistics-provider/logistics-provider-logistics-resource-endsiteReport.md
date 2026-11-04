# logistics.resource.endsiteReport

> 同步物流商数据的接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.logistics.resource.endsiteReport` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/2947 |
| 更新日期 | `2024-06-19` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `brandCode` | body | string | 是 | 驿站品牌的名称 | `mamayizhan` |
| `endSites` | body | array | 是 | 驿站信息列表 | `` |
| `  └ endSiteName` | body | string | 是 | 驿站名称 | `妈妈驿站（北京）` |
| `  └ endSiteCode` | body | string | 是 | 驿站编码 | `AC2312A` |
| `  └ address` | body | object | 是 | 详细地址 | `` |
| `    └ countryCode` | body | string | 是 | 国家编码固定CHN | `CHN` |
| `    └ provinceCode` | body | string | 否 | 驿站在当前物流商省编码 | `11` |
| `    └ provinceName` | body | string | 是 | 驿站在当前物流商省名称 | `北京` |
| `    └ cityCode` | body | string | 否 | 驿站在当前物流商市编码 | `11123312` |
| `    └ cityName` | body | string | 是 | 驿站在当前物流商市名称 | `北京市` |
| `    └ districtCode` | body | string | 否 | 驿站在当前物流商区编码 | `1112331223` |
| `    └ districtName` | body | string | 是 | 驿站在当前物流商区名称 | `朝阳区` |
| `    └ streetCode` | body | string | 否 | 驿站在当前物流商街道编码 | `111233122323` |
| `    └ streetName` | body | string | 否 | 驿站在当前物流商街道名称 | `中关村街道` |
| `    └ detailAddress` | body | string | 是 | 驿站详细地址 | `北京北京市丹棱街5号` |
| `  └ contact` | body | object | 是 | 驿站联系人信息 | `` |
| `    └ name` | body | string | 是 | 驿站联系人姓名 | `张三` |
| `    └ phone` | body | string | 否 | 驿站联系人电话 | `12332121233` |
| `    └ mobile` | body | string | 否 | 驿站联系人手机 | `12332121233` |
| `    └ email` | body | string | 否 | 驿站联系人邮箱 | `zhangsan@bytedance.com` |
| `  └ longitude` | body | string | 是 | 驿站经度 | `111.11` |
| `  └ latitude` | body | string | 是 | 驿站纬度 | `23.11` |
| `  └ serviceStartTime` | body | string | 是 | 驿站营业开始时间24小时制 | `14:00` |
| `  └ serviceEndTime` | body | string | 是 | 驿站营业结束时间24小时制 | `22:00` |
| `  └ endSiteStatus` | body | mixed | 是 | 驿站运营状态1-运营中，2-未运营 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=logistics.resource.endsiteReport&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `err_code` | string | 错误编码 | `0` |
| `err_reason` | string | 错误描述 | `成功` |
| `failRecords` | array | 错误记录 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10001） | 修改请求参数 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10002） | 接口重试 |
| `20000` | 系统错误 / -（sub_code: isp.service-error:10003） | 联系开发人员 |
| `50002` | 业务处理失败 / -（sub_code: isv.business-failed:10206） | 驿站信息存在错误 |

## 响应示例

成功：

```json
{
  "data": {
    "err_code": "0",
    "err_reason": "成功",
    "failRecords": [
      {
        "endSites": {
          "address": {
            "cityCode": "-",
            "cityName": "-",
            "countryCode": "CHN",
            "detailAddress": "-",
            "districtCode": "-",
            "districtName": "-",
            "latitude": "-",
            "longitude": "-",
            "provinceCode": "-",
            "provinceName": "-",
            "streetCode": "-",
            "streetName": "-"
          },
          "contact": {
            "email": "zhangsan@bytedance.com",
            "mobile": "12332121233",
            "name": "张三",
            "phone": "12332121233"
          },
          "endSiteCode": "-",
          "endSiteName": "-",
          "endSiteStatus": "1",
          "latitude": "23.11",
          "longitude": "111.11",
          "serviceEndTime": "22:00",
          "serviceStartTime": "14:00"
        },
        "failDesc": "-"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:10001",
  "sub_msg": "-"
}
```

## 备注
