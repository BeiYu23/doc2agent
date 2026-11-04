# logistics.customTemplateList

> 查询商家自定义区域数据

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics.logistics.customTemplateList` |
| 中文名 | 查询商家自定义区域数据 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/customTemplateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/16/549 |
| 更新日期 | `2021-06-23` |

## 接口说明

- 文档书: 物流发货API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `logistics_code` | body | string | 否 | 物流商编码 | `jtexpress` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/logistics/customTemplateList?app_key=your_appkey_here&method=logistics.customTemplateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `custom_template_data` | array | 自定义模板的数据列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 不支持的服务商（sub_code: isv.business-failed:4006） | 请检查logistics_code字段 |

## 响应示例

成功：

```json
{
  "data": {
    "custom_template_data": [
      {
        "custom_template_infos": [
          {
            "custom_template_code": "C1asaeew2",
            "custom_template_name": "jtexpress自定义模版",
            "custom_template_url": "http://ekdj",
            "parent_template_code": "jtexpress_76_130"
          }
        ],
        "logistics_code": "jtexpress"
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
  "sub_code": "isv.business-failed:4006",
  "sub_msg": "不支持的服务商"
}
```

## 备注
