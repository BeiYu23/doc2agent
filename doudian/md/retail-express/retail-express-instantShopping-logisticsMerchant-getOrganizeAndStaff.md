# instantShopping.logisticsMerchant.getOrganizeAndStaff

> 获取组织架构&人员信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-express.instantShopping.logisticsMerchant.getOrganizeAndStaff` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1584/7299 |
| 更新日期 | `2025-02-24` |

## 接口说明

- 文档书: 合作快递【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `organize_id_list` | body | array | 否 | 组织架构ID集合 | `[]` |
| `staff_id_list` | body | array | 否 | 人员ID集合 | `[]` |
| `ext_info` | body | string | 否 | 订单扩展信息，json格式，线下约定不同承运商的kv结构 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logisticsMerchant.getOrganizeAndStaff&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `organize_list` | array | 组织架构集合 | `` |
| `staff_list` | array | 人员集合 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "organize_list": [
      {
        "organize_code": "\"\"",
        "organize_id": "\"\"",
        "organize_name": "\"\"",
        "organize_type": "1",
        "parent_organize_id": "\"\""
      }
    ],
    "staff_list": [
      {
        "id": "\"\"",
        "name": "\"\"",
        "organize_id": "\"\"",
        "phone": "\"\"",
        "status": "0"
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
