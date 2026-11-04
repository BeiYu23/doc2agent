# 查询商家自定义区模板（新版

> logistics.getCustomTemplateList — 查询商家自定义区模板（新版）

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询商家自定义区模板（新版 |
| 文档地址 | `/docs/doudian/waybill/waybill-logistics-getCustomTemplateList` |
| 接口 ID | `doudian.waybill.logistics.getCustomTemplateList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/getCustomTemplateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/1852 |
| 更新日期 | `2021-08-19` |

## 接口说明

- 文档书: 电子面单API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 否 | 物流服务商编码（若为空代表查询全部） | `shunfeng` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/getCustomTemplateList?app_key=your_appkey_here&method=logistics.getCustomTemplateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `custom_template_data` | array | 商家所有快递自定义模板的数据列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 操作数据库异常（sub_code: isv.business-failed:4010） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_template_data": [
      {
        "custom_template_infos": [
          {
            "custom_template_code": "123",
            "custom_template_id": "1",
            "custom_template_key_list": "1",
            "custom_template_name": "muban",
            "custom_template_url": "1",
            "parent_template_code": "1",
            "parent_template_id": "1"
          }
        ],
        "logistics_code": "shunfeng"
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
  "sub_code": "isv.business-failed:4010",
  "sub_msg": "操作数据库异常"
}
```

## 备注
