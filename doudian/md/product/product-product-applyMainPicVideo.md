# product.applyMainPicVideo

> 应用主图视频至商品

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.product.product.applyMainPicVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/product/applyMainPicVideo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/7048 |
| 更新日期 | `2024-11-18` |

## 接口说明

- 文档书: 商品API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | mixed | 是 | 商品ID | `3506108675121111111` |
| `material_video_id` | body | string | 是 | 主图视频vid，可以先通过https://op.jinritemai.com/docs/api-docs/69/1617接口上传视频，获取审核通过的视频素材ID进行传入 | `v03ecag10000csdkfffog65p65tkkao0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/instituteOrderColonel?app_key=your_appkey_here&method=buyin.instituteOrderColonel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | mixed | 库中素材ID | `7434069266170806000` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 20121060:系统异常\|视频比例校验失败，请重试（sub_code: isv.business-failed:20121060） | 20121060:系统异常\|视频比例校验失败，请重试 |
| `50002` | 业务处理失败 / 2012001:系统异常\|视频比例校验失败，请重试（sub_code: isv.business-failed:2012001） | 2012001:系统异常\|视频比例校验失败，请重试 |
| `50002` | 业务处理失败 / 20121030:主图视频提审失败（sub_code: isv.business-failed:20121030） | 20121030:主图视频提审失败 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_code": "isv.business-failed:20121060",
  "sub_msg": "20121060:系统异常|视频比例校验失败，请重试"
}
```

## 备注
