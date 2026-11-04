# buyin.kolProductsDetail

> 1、本接口用于查询达人视角下单个或批量推广商品的详情；
2、如商品推广不可推广（如下架、清退、封禁等情况下），接口会返回为空；商品状态查询接口：/buyin/materialsProductStatus
3、调用接口前，请先获取精选联盟业务权限：https

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.kolProductsDetail` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/kolProductsDetail` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2866 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_ids` | body | array | 是 | 商品 ID 列表 | `[7234818347981234]` |
| `fields` | body | string | 否 | 需要获取的字段（取products字段下的一级字段，多个用英文逗号隔开，如果不传默认只返回商品基础信息。强烈建议数据按需获取） | `base_info, promotion_info` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/opptyProduct/apply?app_key=your_appkey_here&method=opptyProduct.apply&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `products` | array | 商品列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 商品数过多（sub_code: isv.business-failed:4099） | 参数校验失败: 商品数过多 |
| `50002` | 业务处理失败 / 查询用户信息失败，需要正确的授权角色（sub_code: isv.business-failed:4348） | 查询用户信息失败，需要正确的授权角色 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
