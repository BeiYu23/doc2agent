# 团长托管商品查询

> buyin.colonel.trusteeshipList — 团长托管商品查询

| 元信息 | 值 |
| --- | --- |
| 中文名 | 团长托管商品查询 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-colonel-trusteeshipList` |
| 接口 ID | `doudian.alliance.buyin.colonel.trusteeshipList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonel/trusteeshipList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2137 |
| 更新日期 | `2023-06-20` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | number | 否 | 商品ID | `16234123515826734` |
| `business_id` | body | number | 否 | 商家ID | `461723` |
| `status` | body | string | 否 | 申请状态。0：待审核（默认）；1：生效中；2：已结束 | `2` |
| `sub_status` | body | string | 否 | 子状态（仅当status为已结束时需要传，1:申请未通过; 2:合作已终止; 3:合作已到期） | `1` |
| `page` | body | number | 否 | 页码，从1开始。分页模式下生效，超过10000条会被限制，推荐使用游标模式 retrieve_mode=1 | `1` |
| `page_size` | body | number | 是 | 每页条数（最多20条） | `20` |
| `retrieve_mode` | body | string | 否 | 获取模式。0: 分页模式（默认），最多返回10000条数据；1: 游标模式（推荐），返回条数无限制 | `1` |
| `cursor` | body | string | 否 | 游标。首页不需要传，请求下一页时需传入上一次请求响应的next_cursor值 | `2keoi4023rj34532ko43o` |
| `order_by` | body | number | 否 | 排序（1-按照更新时间倒序） | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 数据总条数 | `100` |
| `records` | array | 托管商品列表 | `` |
| `next_cursor` | string | 下一页游标。游标模式下返回，最后一页返回空 | `3rr32212f24442ffwegrthrt` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍候再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍候再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `40004` | 非法的参数 / sub_status 参数校验失败（当且仅当status为2时必传，1:申请未通过 2:合作已终止 3:合作已到期）（sub_code: isv.parameter-invalid:16384） | 当且仅当status为2时必传，1:申请未通过 2:合作已终止 3:合作已到期 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 无效分页大小（sub_code: isv.business-failed:4097） | 无效分页大小 |
| `40004` | 非法的参数 / 不允许继续翻页，请使用游标模式加载更多数据（sub_code: isv.parameter-invalid:8197） | 请使用游标模式加载更多数据，详情：https://op.jinritemai.com/docs/notice-docs/5/3237 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍候再试"
}
```

## 备注
