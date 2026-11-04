# supplyChain.inspection.GetStandardCollection

> 查询质检标准集

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-goods.supplyChain.inspection.GetStandardCollection` |
| 中文名 | 查询质检标准集 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1523/8267 |
| 更新日期 | `2026-05-06` |

## 接口说明

- 文档书: 供销货品管理（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | mixed | 否 | 类目id | `1000007628` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.inspection.GetStandardCollection&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 返回值 | `` |
| `code` | mixed | 执行编码 | `0` |
| `msg` | string | 执行结果 | `success` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "data": {
      "collection_detail": {
        "collection_code": "=标准集ID_版本号",
        "collection_id": "标准集ID",
        "collection_name": "标准集名称",
        "collection_status": "1",
        "flow_list": [
          {
            "flow_id": "标准流程ID",
            "flow_name": "标准流程名称",
            "item_list": [
              {
                "is_must_inspection": "true",
                "item_code": "标准项ID_版本号",
                "item_detail": "标准项详情",
                "item_id": "标准项ID",
                "item_name": "标准项名称",
                "item_status": "1",
                "material_rule_list": [
                  {
                    "hover_text": "hover文案",
                    "is_must": "true",
                    "lower_limit": "11",
                    "material_name": "材料名称",
                    "material_rule_id": "材料ID",
                    "material_type": "1",
                    "node_type": "catalog",
                    "select_item_list": [
                      {}
                    ],
                    "size_limit": "11",
                    "sub_material_rule_list": [
                      {}
                    ],
                    "upper_limit": "199"
                  }
                ],
                "operate_explain": "操作说明",
                "operate_sample_list": [
                  {
                    "attachment_id": "附件ID",
                    "attachment_type": "1",
                    "file_name": "文件名",
                    "url": "http://xxxxx"
                  }
                ],
                "remark": "备注",
                "version_id": "版本号"
              }
            ],
            "operate_example_list": [
              {
                "attachment_id": "111",
                "attachment_type": "1",
                "file_name": "文件名",
                "url": "http://xxxx"
              }
            ],
            "operate_explain": "操作说明"
          }
        ],
        "version_id": "版本号"
      }
    },
    "msg": "success"
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
