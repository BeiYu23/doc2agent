# 查询团长活动特殊申请

> buyin.colonel.specialApplyList — 查询团长活动特殊申请

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询团长活动特殊申请 |
| 文档地址 | `/docs/doudian/alliance/alliance-buyin-colonel-specialApplyList` |
| 接口 ID | `doudian.alliance.buyin.colonel.specialApplyList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonel/specialApplyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1552 |
| 更新日期 | `2026-04-21` |

## 接口说明

- 文档书: 精选联盟API（版本 V4.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 否 | 活动 id(不传表示查机构下所有活动) | `33241` |
| `search_type` | body | mixed | 否 | 查询类型（0：待处理，1：历史记录，不传默认是待处理） | `0` |
| `page` | body | mixed | 否 | 页数（从 1 开始，不传默认为 1） | `1` |
| `size` | body | mixed | 否 | 每页条数（不传默认为 10，最大为200） | `20` |
| `sort_field` | body | mixed | 否 | 0或不填：以申请时间排序 1：以审核时间排序 | `0,1` |
| `sort_direction` | body | mixed | 否 | 0或不填：降序 1：增序 | `0,1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=buyin.colonel.specialApplyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `special_apply_list` | array | 特殊申请列表 | `` |
| `total` | mixed | 总申请数 | `100` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 4200:账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "special_apply_list": [
      {
        "activity_id": "33241",
        "activity_name": "一个活动",
        "apply_ad_commission_rate": "11.00",
        "apply_ad_service_rate": "5.00",
        "apply_commission_rate": "11.00",
        "apply_cos_type": "1",
        "apply_service_rate": "11.00",
        "apply_time": "2021/12/22 16:55:27",
        "approve_time": "2021/12/22 16:55:27",
        "cur_ad_commission_rate": "11.00",
        "cur_ad_service_rate": "5.00",
        "cur_commission_rate": "10.00",
        "cur_cos_type": "1",
        "cur_service_rate": "10.00",
        "op_type": "1",
        "origin_activity_end_time": "2021/12/22 16:55:27",
        "origin_activity_start_time": "2021/12/22 16:55:27",
        "origin_colonel_buyin_id": "4162341231762354",
        "origin_institution_id": "111",
        "origin_institution_name": "原始团长名称",
        "origin_institution_phone": "6UNGOWt5MkBIgEDQ1I31w==",
        "product_id": "2355245623523",
        "product_img": "https://www.baidu.com",
        "product_name": "iphone13",
        "product_price": "100",
        "product_stock": "11",
        "reason": "处理理由",
        "shop_id": "12343652345",
        "shop_level_is_new": "true",
        "shop_name": "苹果官方旗舰店",
        "shop_phone": "6UNGOWt5MkBIgEDQ1I31w==",
        "shop_score": "4.5",
        "special_apply_id": "13131",
        "status": "0"
      }
    ],
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
