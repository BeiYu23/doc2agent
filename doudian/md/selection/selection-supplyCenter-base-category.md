# 精选货源获取类目

> supplyCenter.base.category — 精选货源获取类目

| 元信息 | 值 |
| --- | --- |
| 中文名 | 精选货源获取类目 |
| 文档地址 | `/docs/doudian/selection/selection-supplyCenter-base-category` |
| 接口 ID | `doudian.selection.supplyCenter.base.category` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5325 |
| 更新日期 | `2023-11-16` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cid` | body | number | 是 | 父类目id，根据父id可以获取子类目。首次请求传值为0 可以获取所有一级类目。循环调用接口获取最小层级类目id，根据响应参数判断is_leaf=true或false。is_leaf=true表示是叶子节点，获取最小层级类目id，is_leaf=false表示不是子节点，请求参数cid=上一次响应参数id，直到获取最小层级类目id。 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.base.category&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照商品类目接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/13/1820 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "enable": "true",
        "id": "20005",
        "is_leaf": "true",
        "level": "1",
        "name": "女装",
        "parent_id": "20215"
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
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照商品类目接口"
}
```

## 备注
