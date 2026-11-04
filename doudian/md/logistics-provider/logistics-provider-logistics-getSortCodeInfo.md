# 获取面单段码信息

> logistics.getSortCodeInfo — 获取面单段码信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取面单段码信息 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-logistics-getSortCodeInfo` |
| 接口 ID | `doudian.logistics-provider.logistics.getSortCodeInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getSortCodeInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/6823 |
| 更新日期 | `2026-06-10` |

## 接口说明

- 文档书: 物流商API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `track_no` | body | string | 是 | 运单号 | `123456789` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getSortCodeInfo?app_key=your_appkey_here&method=logistics.getSortCodeInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `current_result` | object | 实时的字节计算结果 | `` |
| `result_flag` | string | 取号时的结果采纳方 | `123` |
| `track_no` | string | 运单号 | `123` |
| `express_result` | object | 取号时的物流商计算结果 | `` |
| `snap_result` | object | 取号时的字节计算结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 4006:该面单不存在（sub_code: isv.business-failed:4006） | 4006:该面单不存在 |

## 响应示例

成功：

```json
{
  "data": {
    "current_result": {
      "calc_net_code": "123",
      "first_sort_code": "123",
      "first_sort_code_conf": "{}",
      "intervene_info": "{}",
      "intervene_type": "123",
      "mark_destination_code": "123",
      "mark_destination_code_name": "大头笔",
      "model_type": "123",
      "package_code": "123",
      "package_code_name": "集包地",
      "second_sort_code": "123",
      "second_sort_code_conf": "{}",
      "third_sort_code": "123"
    },
    "express_result": {
      "calc_net_code": "123",
      "first_sort_code": "123",
      "first_sort_code_conf": "123",
      "intervene_info": "123",
      "intervene_type": "1",
      "mark_destination_code": "123",
      "mark_destination_code_name": "1",
      "model_type": "1",
      "package_code": "1",
      "package_code_name": "123",
      "second_sort_code": "123",
      "second_sort_code_conf": "1",
      "third_sort_code": "1"
    },
    "result_flag": "123",
    "snap_result": {
      "calc_net_code": "1",
      "first_sort_code": "1",
      "first_sort_code_conf": "1",
      "intervene_info": "1",
      "intervene_type": "1",
      "mark_destination_code": "1",
      "mark_destination_code_name": "1",
      "model_type": "1",
      "package_code": "1",
      "package_code_name": "1",
      "second_sort_code": "1",
      "second_sort_code_conf": "1",
      "third_sort_code": "1"
    },
    "track_no": "123"
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
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "4006:该面单不存在"
}
```

## 备注
