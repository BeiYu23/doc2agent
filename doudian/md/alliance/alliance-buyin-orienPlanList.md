# buyin.orienPlanList

> 商品定向计划查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.buyin.orienPlanList` |
| 中文名 | 商品定向计划查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/buyin/orienPlanList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/705 |
| 更新日期 | `2021-08-06` |

## 接口说明

- 文档书: 精选联盟API（版本 V1.06）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 否 | 分页。最小值取1，最大取100 | `1` |
| `page_size` | body | number | 否 | 每页数目。默认20，最大40 | `20` |
| `product_id` | body | number | 否 | 按商品ID搜索 | `3482204602722574252` |
| `product_name` | body | string | 否 | 按商品名称搜索 | `测试商品` |
| `orien_plan_id` | body | string | 否 | 定向计划ID | `1231` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/orienPlanList?app_key=your_appkey_here&method=buyin.orienPlanList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 定向计划总数 | `122` |
| `orien_plans` | array | 商品定向计划列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 商家已被关闭推广，无法使用平台功能（sub_code: isv.business-failed:4102） | 商家已被关闭推广，无法使用平台功能 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍候再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍候再试 |
| `50002` | 业务处理失败 / 4101:商家未同意百应协议（sub_code: isv.business-failed:4101） | 4101:商家未同意百应协议 |
| `50002` | 业务处理失败 / 4096:获取店铺ID失败（sub_code: isv.business-failed:4096） | 4096:获取店铺ID失败 |

## 响应示例

成功：

```json
{
  "data": {
    "orien_plans": [
      {
        "orien_plans": [
          {
            "apply_type": "1",
            "audit_type": "1",
            "author_level": "1",
            "cos_ratio": "50",
            "cover": "https://tosv.boe.byted.org/obj/temai/7e92a281163e33cedef99d8735d1e90bwww828-708",
            "create_time": "1625480546",
            "end_time": "1625480546",
            "kol_num": "1",
            "new_cos_ratio": "0",
            "new_cos_ratio_start_time": "1625480546",
            "orien_plan_id": "111",
            "plan_status": "2",
            "price": "120",
            "product_id": "3482204602722574252",
            "product_name": "测试商品",
            "restricted_type": "1",
            "start_time": "1625480546"
          }
        ],
        "product_id": "3482204602722574252"
      }
    ],
    "total": "122"
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
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
