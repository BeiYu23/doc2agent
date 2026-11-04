# inspection.getStandardCollection

> 查询质检标准集

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.inspection.getStandardCollection` |
| 中文名 | 查询质检标准集 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/inspection/getStandardCollection` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8254 |
| 更新日期 | `2026-04-28` |

## 接口说明

- 文档书: 行业API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 是 | 类目id | `1000007628` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/inspection/getStandardCollection?app_key=your_appkey_here&method=inspection.getStandardCollection&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回数据 | `` |
| `code` | mixed | 响应code | `0` |
| `msg` | string | 响应message | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 缺少必选参数 (如：operator_info 身份信息为空 或 category_id 为空)（sub_code: isv.missing-parameter:-41003） | 请检查并传入必传参数 operator_info.operator_id 和 category_id |
| `50002` | 业务处理失败 / 业务处理失败 (如：获取标准类目失败)（sub_code: isv.business-failed:-41005） | 请检查参数有效性，或稍后重试 |
| `20000` | 系统错误 / 服务不可用 (如：获取标准类目服务返回为空)（sub_code: isp.service-error:-41002） | 系统内部繁忙或异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "collection_detail": {
        "collection_code": "7457180029220159759_152",
        "collection_id": "7457180029220159759",
        "collection_name": "二手已验机信息回传标准集（置信大商）",
        "collection_status": "1",
        "flow_list": [
          {
            "flow_id": "7611460237148815643",
            "flow_name": "基础信息",
            "item_list": [
              {
                "is_must_inspection": "true",
                "item_code": "7457181828446535988_2",
                "item_detail": "可检测才回传（置信大商）",
                "item_id": "7457181828446535988",
                "item_name": "购买渠道",
                "item_status": "1",
                "material_rule_list": [
                  {
                    "hover_text": "选择后实操端展示可选项，请在输入框内输入选项枚举值",
                    "is_must": "true",
                    "lower_limit": "1",
                    "material_name": "单行文本",
                    "material_rule_id": "7570985732199858432",
                    "material_type": "5",
                    "node_type": "leaf",
                    "select_item_list": [
                      {}
                    ],
                    "size_limit": "0",
                    "sub_material_rule_list": [
                      {}
                    ],
                    "upper_limit": "20"
                  }
                ],
                "operate_explain": "",
                "operate_sample_list": [
                  {
                    "attachment_id": "7580311243121312054",
                    "attachment_type": "100",
                    "file_name": "file_name",
                    "url": "xxx"
                  }
                ],
                "remark": "备注",
                "version_id": "2"
              }
            ],
            "operate_example_list": [
              {
                "attachment_id": "7580311243121312054",
                "attachment_type": "100",
                "file_name": "file_name",
                "url": "xx"
              }
            ],
            "operate_explain": "xx"
          }
        ],
        "version_id": "152"
      }
    },
    "msg": ""
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:-41003",
  "sub_msg": "缺少必选参数 (如：operator_info 身份信息为空 或 category_id 为空)"
}
```

## 备注
