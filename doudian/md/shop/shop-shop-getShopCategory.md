# 请一定使用最小层级类目id，发布商品或更新商品

> shop.getShopCategory — 请一定使用最小层级类目id，发布商品或更新商品。
接口使用注意点：
1、第一次请求cid=0获取所有一级类目
2、先判断enable=true，如果enable=false表示该类目已经失效，请勿使用。
3、循环获取最小层级类目id方式：再判断is_lea

| 元信息 | 值 |
| --- | --- |
| 中文名 | 请一定使用最小层级类目id，发布商品或更新商品 |
| 文档地址 | `/docs/doudian/shop/shop-shop-getShopCategory` |
| 接口 ID | `doudian.shop.shop.getShopCategory` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/getShopCategory` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/13/1820 |
| 更新日期 | `2026-01-21` |

## 接口说明

- 文档书: 店铺API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `cid` | body | number | 是 | 父类目id，根据父id可以获取子类目。首次请求传值为0 可以获取所有一级类目。循环调用接口获取最小层级类目id，根据响应参数判断is_leaf=true或false。is_leaf=true表示是叶子节点，获取最小层级类目id，is_leaf=false表示不是子节点，请求参数cid=上一次响应参数id，直到获取最小层级类目id。 | `0` |
| `channel` | body | string | 否 | 类目渠道，0：门捷列夫类目，1：标准类目； | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 返回参数列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2012004） | 检查参数 |
| `50002` | 业务处理失败 / 获取类目信息失败（sub_code: isv.business-failed:2012013） | 重试 |
| `50002` | 业务处理失败 / 获取商家信息失败，请重试（sub_code: isv.business-failed:2012001） | 重试 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:2012004",
  "sub_msg": "参数错误"
}
```

## 备注
