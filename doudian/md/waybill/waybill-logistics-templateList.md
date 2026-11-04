# logistics.templateList

> 查询物流商的标准模板。
注意：物流商模板平台会定期更新或新增，请开发者定期扫描该接口，保持和平台数据一致；

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.templateList` |
| 中文名 | 查询物流商的标准模板 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/templateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/476 |
| 更新日期 | `2021-06-22` |

## 接口说明

- 文档书: 电子面单API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/templateList?app_key=your_appkey_here&method=logistics.templateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_data` | array | 模版数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 100201:获取模版信息失败（sub_code: isv.business-failed:100201） | 请重试 |

## 响应示例

成功：

```json
{
  "data": {
    "template_data": [
      {
        "logistics_code": "ems",
        "template_infos": [
          {
            "perview_url": "https://lf9-cm.ecombdstatic.com/obj/logistics-davinci/preview/jt_100_180.png",
            "template_code": "ems_100_180",
            "template_id": "14",
            "template_name": "EMS二联单",
            "template_type": "2",
            "template_url": "https://lf3-cm.ecombdstatic.com/obj/logistics-YOUR_SECRET_KEY_ems100.xml",
            "version": "1"
          }
        ]
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
  "sub_code": "isv.business-failed:100201",
  "sub_msg": "100201:获取模版信息失败"
}
```

## 备注
