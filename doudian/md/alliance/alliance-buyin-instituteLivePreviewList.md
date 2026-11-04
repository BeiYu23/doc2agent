# buyin.instituteLivePreviewList

> 获取直播预告及商品信息列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.instituteLivePreviewList` |
| 中文名 | 获取直播预告及商品信息列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/instituteLivePreviewList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/2224 |
| 更新日期 | `2025-06-26` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `buyin_id` | body | string | 是 | 要查询的达人的百应ID | `6945289506111766791` |
| `need_product_info` | body | boolean | 否 | 是否需要预告对应的商品信息。需要商品信息会增加接口耗时，默认false | `false` |
| `page` | body | mixed | 否 | 页码，从1开始 | `1` |
| `page_size` | body | mixed | 否 | 每页直播预告数量，最大100 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/instituteLivePreviewList?app_key=your_appkey_here&method=buyin.instituteLivePreviewList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 预告总数 | `1` |
| `previews` | array | 直播预告及商品信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效分页大小（sub_code: isv.parameter-invalid:4127） | 参数校验失败: 无效分页大小 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:4097） | 参数校验失败 |
| `40004` | 非法的参数 / 无效百应ID（sub_code: isv.parameter-invalid:4098） | 无效百应ID |
| `50002` | 业务处理失败 / 服务打瞌睡了，下游服务调用错误（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `40004` | 非法的参数 / 达人未开通分销业务（sub_code: isv.parameter-invalid:4129） | 请输入开通分销业务的达人buyinId |
| `40004` | 非法的参数 / 当前达人没有直播预告功能权限（sub_code: isv.parameter-invalid:4109） | 请输入开通直播预告权限的达人buyinId |
| `50002` | 业务处理失败 / 需【抖客】角色授权后访问（sub_code: isv.business-failed:8194） | 需【抖客】角色授权后访问 |

## 响应示例

成功：

```json
{
  "data": {
    "previews": [
      {
        "booking_num": "20",
        "preview_id": "1234567",
        "product_count": "6",
        "products": [
          {
            "ads_promotion_ratio": {
              "old_fans_ratio": "500",
              "share_ratio": "1000"
            },
            "category_id": "29187",
            "cover": "https://p6-aio.ecombdimg.com/obj/temai/6ef6ccb6699c9865be7e68c325bf22e7w",
            "first_cid": "20018",
            "first_cname": "零食/坚果/特产",
            "list_num": "1",
            "preview_price": "1000",
            "price": "1000",
            "product_desc": "满100减20",
            "product_id": "3094093204930502",
            "second_cid": "20313",
            "second_cname": "饼干/膨化",
            "third_cid": "22977",
            "third_cname": "饼干",
            "title": "测试商品岩烧芝士脆饼干"
          }
        ],
        "start_time": "1658095200"
      }
    ],
    "total": "1"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:4127",
  "sub_msg": "无效分页大小"
}
```

## 备注
