# superm.product.queryProductSyncTask

> 查询异步执行的根任务列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.superm.product.queryProductSyncTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/queryProductSyncTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2696 |
| 更新日期 | `2023-04-10` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `task_type` | body | string | 是 | 任务类型。支持的任务类型有：batch_redistribute_sub_product - 重新分配店铺主品对应的门店子品; sync_sub_products_price - 将店铺主品的价格应用至门店子品；sync_sub_products - 主商品变更后变更结果同步至子商品 | `batch_redistribute_sub_product` |
| `task_id` | body | number | 否 | 任务ID | `7158439918014824735` |
| `page` | body | number | 是 | 起始页 (从0开始) | `0` |
| `size` | body | number | 是 | 每页尺寸 (最大值50) | `10` |
| `product_id` | body | number | 否 | 主商品ID，传入则查询该主商品的相关任务 | `3xxxxxxxxxxxxxxxxxxx` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_list` | array | 任务列表 | `` |
| `page` | number | 起始页 (从0开始) | `0` |
| `size` | number | 每页尺寸 (最大值50) | `10` |
| `total` | number | 任务总数 | `30` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010001:查询Task信息出错，请稍后重试（sub_code: isv.business-failed:2010001） | 请稍后重试 |
| `50002` | 业务处理失败 / 2010004:当前登录的用户信息不合法（sub_code: isv.business-failed:2010004） | 2010004:当前登录的用户信息不合法 |

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
  "sub_code": "isv.business-failed:2010001",
  "sub_msg": "2010001:查询Task信息出错，请稍后重试"
}
```

## 备注
