# product.setOffline

> 1、支持所有类型商品下架
2、接口调用成功，商品会放到仓库中

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.setOffline` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/setOffline` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/252 |
| 更新日期 | `2024-03-05` |

## 接口说明

- 文档书: 商品API（版本 V1.07）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 是 | 商品ID | `356654869456454` |
| `outer_product_id` | body | string | 否 | 推荐使用，外部商家编码，支持字符串。 | `2333424` |
| `store_id` | body | number | 否 | 小时达二期店铺场景才可以传，小时达二期场景可以通过传入主品id+门店id对该门店下的子品进行操作 | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 【状态非法】商品状态错误, 当前状态: 删除（sub_code: isv.parameter-invalid:2010022） | 请重新选择商品 |
| `40004` | 非法的参数 / 【重复操作】商品操作重复，当前状态：下架（sub_code: isv.parameter-invalid:2010021） | 请重新选择商品 |
| `40004` | 非法的参数 / 下架失败，该商品正在参加平台秒杀-抖in好物池（自播专入），暂不支持下架（sub_code: isv.parameter-invalid:2010005） | 请重新选择商品 |
| `40004` | 非法的参数 / 奖品商品不支持下架（sub_code: isv.parameter-invalid:2010004） | 请重新选择商品 |
| `40004` | 非法的参数 / 缺少必要参数（sub_code: isv.parameter-invalid:20024） | 请检查参数后重试 |
| `40004` | 非法的参数 / 商户状态不合法（sub_code: isv.parameter-invalid:10008） | 请检查店铺状态 |
| `50002` | 业务处理失败 / 请求超时（sub_code: isv.business-failed:2010002） | 请稍后重试 |
| `50002` | 业务处理失败 / 更新商品失败（sub_code: isv.business-failed:2010001） | 请稍后重试 |
| `50002` | 业务处理失败 / 商品正在参加平台活动，无法下架商品（sub_code: isv.business-failed:2010045） | 商品正在参加平台活动，无法下架商品 |
| `50002` | 业务处理失败 / 商品不存在（sub_code: isv.business-failed:2010064） | 请检查product_id信息 |
| `50002` | 业务处理失败 / 2010058:商品不存在（sub_code: isv.business-failed:2010058） | 请检查product_id信息 |
| `50002` | 业务处理失败 / 2010401:请求被限流, 请稍后再试（sub_code: isv.business-failed:2010401） | 请稍后重试 |
| `50002` | 业务处理失败 / 2010013:获取账号信息失败（sub_code: isv.business-failed:2010013） | 请稍后重试 |
| `50002` | 业务处理失败 / 7:获取子商品信息失败（sub_code: isv.business-failed:7） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110310134:奖品下架失败, 该奖品有合作中的权益活动（sub_code: isv.business-failed:110310134） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110101052:赠品有关联未失效的赠品活动、不可下架（sub_code: isv.business-failed:110101052） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110310132:奖品下架失败, 该奖品已绑定抽奖活动（sub_code: isv.business-failed:110310132） | 请检查入参信息 |
| `50002` | 业务处理失败 / 110211010:已有库存占用，无法修改绑定关系（sub_code: isv.business-failed:110211010） | 110211010:已有库存占用，无法修改绑定关系 |

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
  "sub_code": "isv.parameter-invalid:2010022",
  "sub_msg": "【状态非法】商品状态错误, 当前状态: 删除"
}
```

## 备注
