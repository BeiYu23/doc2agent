# 查询配送费满减活动下生效的门店

> instantShopping.marketing.listShopFreightDiscountStores — 查询配送费满减活动下生效的门店

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询配送费满减活动下生效的门店 |
| 文档地址 | `/docs/doudian/retail-marketing/retail-marketing-instantShopping-marketing-listShopFreightDiscountStores` |
| 接口 ID | `doudian.retail-marketing.instantShopping.marketing.listShopFreightDiscountStores` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1541/7552 |
| 更新日期 | `2025-07-03` |

## 接口说明

- 文档书: 营销管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 是 | 当前页码，从1开始 | `1` |
| `size` | body | mixed | 是 | 分页大小 | `10` |
| `activity_id` | body | string | 是 | 活动ID | `123` |
| `store_ids` | body | array | 否 | 根据门店id列表批量查询 | `[111,222,333]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.marketing.listShopFreightDiscountStores&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 店铺信息 | `` |
| `total` | mixed | 查询总量 | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-40000） | 检查请求参数 |
| `40004` | 非法的参数 / 越权错误（sub_code: isv.parameter-invalid:-50001） | 检查当前用户是否有权限操作 |
| `20001` | 内部服务超时 / 系统繁忙，请稍后重试（sub_code: isp.service-timeout-error:-10000） | 系统繁忙，请稍后重试 |
| `20000` | 系统错误 / 系统异常，请联系技术人员排查（sub_code: isp.service-error:-11450） | 系统异常，请联系技术人员排查 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "store_id": "123",
        "store_name": "测试店铺"
      }
    ],
    "total": "123"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-40000",
  "sub_msg": "参数不合法"
}
```

## 备注
