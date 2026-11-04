# 查询店铺的类目信息

> shop.marketCategoryQuery — 查询店铺的类目信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询店铺的类目信息 |
| 文档地址 | `/docs/doudian/decoration/decoration-shop-marketCategoryQuery` |
| 接口 ID | `doudian.decoration.shop.marketCategoryQuery` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/marketCategoryQuery` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/2902 |
| 更新日期 | `2024-03-05` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `parent_category_id` | body | number | 否 | 父类目的id，不传则category_id表示一级类目 | `7184332308881850668` |
| `category_id` | body | number | 否 | 类目的id，查询特定类目时必传，不传则查询全部类目 | `7184332308881850668` |
| `tmp_id` | body | number | 否 | 页面ID，需要查询的页面。 | `7184332308881850668` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=yunc.wms.inbound.createSaleOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `category_info_list` | array | 类目 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数检验不通过（sub_code: isv.parameter-invalid:20130） | 请检查参数是否合法，是否是有效的类目信息 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:20131） | 处理失败，请重试或联系客服处理 |
| `50002` | 业务处理失败 / 没有可编辑的分类页版本，请到商家后台创建并生效（sub_code: isv.business-failed:20111） | 需要在pc端先将页面发布生效 |
| `50002` | 业务处理失败 / 存在多个生效的页面,请指定tmpId（sub_code: isv.business-failed:23000） | 需要指定tmp_id |
| `50002` | 业务处理失败 / 20110:商家分类页未生效,请先到管理端发布页面.（sub_code: isv.business-failed:20110） | 20110:商家分类页未生效,请先到管理端发布页面. |

## 响应示例

成功：

```json
{
  "data": {
    "data": "{}"
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
  "sub_code": "isv.parameter-invalid:20130",
  "sub_msg": "参数检验不通过"
}
```

## 备注
