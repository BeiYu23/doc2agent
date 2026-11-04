# 即时零售

> shop.GetProdCateRelation — 即时零售，分类页场景，通过商品ID查询对应关联的页面分类信息。仅返回映射关系，具体生效情况，以查询到的tmp_id、cate_id查询为准。 如果页面是下线状态，仍可以查询到映射关系。

无法查询的原因：
1.  绑定关系不存在。
2. 绑定的分类已经被删

| 元信息 | 值 |
| --- | --- |
| 中文名 | 即时零售 |
| 文档地址 | `/docs/doudian/decoration/decoration-shop-GetProdCateRelation` |
| 接口 ID | `doudian.decoration.shop.GetProdCateRelation` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/GetProdCateRelation` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6874 |
| 更新日期 | `2024-09-12` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id_list` | body | array | 否 | 店铺主品信息，单次限制查询50个以内。商品状态需要是上架、审核通过。 | `[ "3706833482023043077", "3706838030552793344"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comcrossborder/msg/push?app_key=your_appkey_here&method=crossborder.msg.push&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `pid_cid_map` | string | 商品对应前台类目信息 | `object` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
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
