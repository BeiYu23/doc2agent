# buyin.originColonelUnappliedProductList

> 团长获取可提报二级团长活动的商品列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.originColonelUnappliedProductList` |
| 中文名 | 团长获取可提报二级团长活动的商品列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/originColonelUnappliedProductList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1677 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | mixed | 否 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 是 | 每页条数，最大20 | `20` |
| `activity_id` | body | mixed | 是 | 活动ID | `54321` |
| `product_info` | body | string | 否 | 商品名称 or 商品ID | `一个商品` |
| `retrieve_mode` | body | mixed | 否 | 获取模式。0: 分页模式（默认），最多返回10000条数据；1: 游标模式（推荐），返回条数无限制 | `1` |
| `cursor` | body | string | 否 | 游标。首页不需要传，请求下一页时需传入上一次请求响应的next_cursor值 | `cefe2r3r2332dcd2/ddf32` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/originColonelUnappliedProductList?app_key=your_appkey_here&method=buyin.originColonelUnappliedProductList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 数据 | `` |
| `total` | mixed | 总数 | `100` |
| `next_cursor` | string | 下一页游标。游标模式下返回，最后一页返回空 | `ee2k23i492njwtio5j435ij34n5n34` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "ad_commission_rate": "10.5",
        "ad_service_rate": "5.5",
        "applied_by_others": "true",
        "can_apply": "true",
        "can_promote": "true",
        "cannot_apply_reason": "商品未开启普通计划，暂不支持报名",
        "category_id": "1",
        "category_name": "1对应的类目名称",
        "commission_rate": "10.5",
        "cos_type": "1",
        "origin_activity_id": "51261",
        "origin_activity_name": "原始团长名称",
        "product_id": "73618234123",
        "product_img": "https:www.baidu.com",
        "product_name": "一个商品",
        "product_price": "100",
        "product_stock": "100",
        "promote_end_time": "2022-02-20",
        "promote_start_time": "2022-01-10",
        "service_rate": "10.5",
        "update_time": "1688356428"
      }
    ],
    "next_cursor": "ee2k23i492njwtio5j435ij34n5n34",
    "total": "100"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
