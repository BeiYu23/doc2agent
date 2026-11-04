# 接口用于团长获取可参与的二级团长活动

> buyin.originColonelEnrollableActivityList — 接口用于团长获取可参与的二级团长活动，支持报名状态筛选，包括已提报和未提报两种状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 接口用于团长获取可参与的二级团长活动 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-originColonelEnrollableActivityList` |
| 接口 ID | `doudian.alliance.buyin.originColonelEnrollableActivityList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/originColonelEnrollableActivityList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1675 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.11）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `apply_status` | body | string | 是 | 1、我报名的活动 2、可以报名的活动 | `1` |
| `page` | body | number | 否 | 页码，从1开始。分页模式下生效，超过10000条会被限制 | `1` |
| `page_size` | body | number | 否 | 每页条数，最大20 | `20` |
| `commission_rate_min` | body | string | 否 | 活动要求的最低佣金率，例：5%传5 | `5` |
| `commission_rate_max` | body | string | 否 | 活动要求的最高佣金率，例：5%传5 | `5` |
| `service_rate_min` | body | string | 否 | 活动要求的最低服务费率，例：5%传5 | `5` |
| `service_rate_max` | body | string | 否 | 活动要求的最高服务费率，例：5%传5 | `5` |
| `product_category_id` | body | string | 否 | 类目ID | `1` |
| `inst_acti_name` | body | string | 否 | 团长名称或活动名称-模糊搜索 | `一个团长` |
| `retrieve_mode` | body | string | 否 | 获取模式。0: 分页模式（默认），最多返回10000条数据；1: 游标模式（推荐），返回条数无限制 | `1` |
| `cursor` | body | string | 否 | 游标。游标模式下传，首页不需要传 | `mdqwje3iorji3nr3j../fd` |
| `colonel_buyin_id` | body | number | 否 | 团长百应 id | `4739745019873796` |
| `cos_limit_type` | body | string | 否 | 佣金限制类型，1:不限制 2:仅双佣金 3:仅固定佣金 | `1` |
| `ad_commission_rate_min` | body | string | 否 | 双佣金投放期佣金率min，例：5%传5 | `5` |
| `ad_commission_rate_max` | body | string | 否 | 双佣金投放期佣金率max，例：5%传5 | `5` |
| `ad_service_rate_min` | body | string | 否 | 双佣金投放期服务费率min，例：5%传5 | `5` |
| `ad_service_rate_max` | body | string | 否 | 双佣金投放期服务费率max，例：5%传5 | `5` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 数据 | `` |
| `total` | number | 总数，游标模式下不返回 | `100` |
| `next_cursor` | string | 下一页游标。游标模式下返回，最后一页返回空 | `fdkdfjie../32321jckld` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `40004` | 非法的参数 / 不允许继续翻页，请使用游标模式加载更多数据（sub_code: isv.parameter-invalid:8197） | 请使用游标模式加载更多数据 |
| `50002` | 业务处理失败 / 账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 账号状态异常，请检查账号状态 |
| `50002` | 业务处理失败 / 16384:非法团长百应 id（sub_code: isv.business-failed:16384） | 16384:非法团长百应 id |

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
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
