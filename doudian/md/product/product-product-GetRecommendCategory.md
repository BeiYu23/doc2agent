# product.GetRecommendCategory

> 商品类目预测

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.GetRecommendCategory` |
| 中文名 | 商品类目预测 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/GetRecommendCategory` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/2004 |
| 更新日期 | `2026-03-12` |

## 接口说明

- 文档书: 商品API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `scene` | body | string | 是 | category_infer: 基于标题、图片等推断商品类目；predict_by_title_and_img：基于标题、图片等推断商品类目（图片必传）； | `product_info` |
| `pic` | body | array | 否 | 商品主图图片url，scene为predict_by_title_and_img时必传 | `` |
| `  └ url` | body | string | 是 | 图片链接，必须是素材中心的url | `https://p3-aio.ecombdimg.com/obj/ecom-shop-material/v1_GhxlaZ_70852585116381186630419_c55b8401b00e96e4114431a1dbd7c99c_sx_582346_www1000-1000` |
| `category_leaf_id` | body | mixed | 否 | 商品类目id，无需传递 | `20415` |
| `name` | body | string | 否 | 商品标题 | `商品标题` |
| `product_format_new` | body | string | 否 | 商品类目属性 | `{}` |
| `  └ value` | body | mixed | 否 | 属性id | `32314111111` |
| `  └ name` | body | string | 否 | 属性名称 | `衣长1` |
| `standard_brand_id` | body | mixed | 否 | 品牌id | `30241` |
| `async_task_id` | body | string | 否 | 深度思考异步任务ID，命中深度思考时返回，用于轮询深度思考结果 | `task-123` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/GetRecommendCategory?app_key=your_appkey_here&method=product.GetRecommendCategory&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `categoryDetails` | array | 推荐类目结果 | `` |
| `recommend_id` | string | 类目预测记录id | `qwertyui123456` |
| `async_task_id` | string | 深度思考异步任务ID，命中深度思考时返回，用于轮询深度思考结果 | `task-123` |
| `async_task_status` | mixed | 深度思考任务状态，命中深度思考时返回。0-init 1-running 2-success 3-failed | `2` |
| `timeout` | mixed | 深度思考超时时间，单位：ms，命中深度思考时返回，用于轮询深度思考结果 | `10000` |
| `interval` | mixed | 深度思考轮询间隔，单位：ms，命中深度思考时返回，用于轮询深度思考结果 | `1000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误（sub_code: isp.service-error:2010001） | 重试 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:2010004） | 检查参数 |
| `50002` | 业务处理失败 / 2010013:获取账号信息失败（sub_code: isv.business-failed:2010013） | 获取账号信息失败，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "async_task_id": "task-123",
    "async_task_status": "2",
    "categoryDetails": [
      {
        "category_detail": {
          "first_cid": "20131",
          "first_cname": "一级类目名称",
          "fourth_cid": "154325",
          "fourth_cname": "四级类目名称",
          "second_cid": "34234",
          "second_cname": "二级类目名称",
          "third_cid": "13144",
          "third_cname": "三级类目名称"
        },
        "qualification_status": "1"
      }
    ],
    "interval": "1000",
    "recommend_id": "qwertyui123456",
    "timeout": "10000"
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
  "sub_code": "isp.service-error:2010001",
  "sub_msg": "系统错误"
}
```

## 备注
