# 查询类目下需要填写的商品资质

> supplyCenter.base.qualificationConfig — 查询类目下需要填写的商品资质

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询类目下需要填写的商品资质 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-base-qualificationConfig` |
| 接口 ID | `doudian.selection.supplyCenter.base.qualificationConfig` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5327 |
| 更新日期 | `2023-10-25` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 是 | 叶子类目ID | `123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.base.qualificationConfig&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `config_list` | array | 资质列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品资质类目（sub_code: isv.parameter-invalid:666666） | https://op.jinritemai.com/docs/api-docs/14/1382 |

## 响应示例

成功：

```json
{
  "data": {
    "config_list": [
      {
        "is_required": "true",
        "key": "3457058945162709852",
        "matchable_rule": [
          {
            "is_qualification_required": "true",
            "rule_clause": {}
          }
        ],
        "name": "质检报告",
        "text_list": "[ \"需为近一年由第三方权威质检机构出具的一份含有CMA或CNAS认证的质检报告。\", \"-检测报告里的商品名称、品牌、生产商名称等信息与商详发布的商品信息需一致\", \"-如报告无品牌名称，需提供含品牌名称、商品名称及生产单位的产品实拍图\", \"-涉及特殊材质的商品，需提供材质（面料）或成品质检报告，质检报告须包含材质成分（纺织品还需包含面料含量)、对应的商品货号或款号或商品名称。特殊材质包含但不限于蚕丝、真丝、羽绒、鸭绒、鹅绒、羊绒、羊毛、牛皮、羊皮、真皮、移膜革、猪皮等（包括皮草类）。\" ]"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:666666",
  "sub_msg": "参照商品资质类目"
}
```

## 备注
