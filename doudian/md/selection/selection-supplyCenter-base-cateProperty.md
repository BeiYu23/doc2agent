# 精选货源获取类目属性

> supplyCenter.base.cateProperty — 精选货源获取类目属性

| 元信息 | 值 |
| --- | --- |
| 中文名 | 精选货源获取类目属性 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-base-cateProperty` |
| 接口 ID | `doudian.selection.supplyCenter.base.cateProperty` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5326 |
| 更新日期 | `2023-10-25` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_leaf_id` | body | number | 是 | 叶子类目id | `1332132` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.base.cateProperty&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回列表 | `` |
| `tpl_type` | number | 模板类型，SPU为1，结构化为2，默认为0（无特殊需求忽略该字段即可） | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照类目属性接口（sub_code: isv.parameter-invalid:6666666） | https://op.jinritemai.com/docs/api-docs/14/1373 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "category_id": "31918",
        "diy_type": "1",
        "has_sub_property": "false",
        "important_type": "1",
        "multi_select_max": "5",
        "options": [
          {
            "name": "ON:THE BODY/安宝笛",
            "sequence": "2",
            "value": "1062254699",
            "value_id": "1"
          }
        ],
        "property_id": "14133",
        "property_name": "材质",
        "property_type": "1",
        "relation_id": "1",
        "required": "0",
        "sequence": "2",
        "status": "1",
        "type": "text"
      }
    ],
    "tpl_type": "2"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:6666666",
  "sub_msg": "参照类目属性接口"
}
```

## 备注
