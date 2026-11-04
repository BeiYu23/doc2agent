# buyin.colonelExtendApplyList

> 专属团长活动商品延时申请结果查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.colonelExtendApplyList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/colonelExtendApplyList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2430 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | number | 否 | 活动 id | `5253123` |
| `product_id` | body | number | 否 | 商品 id | `36213412341234` |
| `status` | body | array | 是 | 状态：1-待审核,2-商家同意,3-商家拒绝,4-自动拒绝（如果状态列表有1，则只查询待审核的延长申请，没有1，则查询所有传入状态的延长申请） | `1` |
| `page` | body | number | 否 | 页码（默认1） | `1` |
| `size` | body | number | 否 | 每页条数（默认20，最大20） | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/colonelExtendApplyList?app_key=your_appkey_here&method=buyin.colonelExtendApplyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `extend_applies` | array | 延长申请列表 | `` |
| `total` | number | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 257:参数校验失败（sub_code: isv.business-failed:257） | 257:参数校验失败 |

## 响应示例

成功：

```json
{
  "data": {
    "extend_applies": [
      {
        "activity_id": "523412",
        "end_time": "2006-01-02 15:04:05",
        "origin_activity_id": "512345",
        "origin_buyin_id": "32641726341238742",
        "product_id": "4361723412342154",
        "product_img": "https://www.baidu.com",
        "product_name": "商品名称",
        "status": "1",
        "update_time": "2006-01-02 15:04:05"
      }
    ],
    "total": "10"
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
  "sub_code": "isv.business-failed:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
