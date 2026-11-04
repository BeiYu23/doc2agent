# shopVideo.publishVideo

> 投稿短视频

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.publishVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/publishVideo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7145 |
| 更新日期 | `2025-01-13` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `anchor_list` | body | array | 否 | 短视频锚点（关联商品） | `` |
| `  └ type` | body | mixed | 否 | 锚点类型：3-国内电商（挂车），7-电商种草 | `3` |
| `  └ product_ids` | body | array | 否 | 锚点关联商品id，当前只支持关联一个商品 | `[1]` |
| `basic_info` | body | object | 是 | 短视频基础信息 | `` |
| `  └ media_id` | body | string | 是 | 视频id | `v0d27cg10001csve2qfog65o283c1h0g` |
| `  └ desc` | body | string | 否 | 描述 | `描述` |
| `  └ title` | body | string | 否 | 标题 | `标题` |
| `  └ activity_list` | body | array | 否 | 活动列表 | `` |
| `    └ activity_id` | body | string | 否 | 活动id | `2222` |
| `    └ activity_name` | body | string | 否 | 活动名称 | `蛋仔派对互动玩法开播活动` |
| `  └ cover_image_uri` | body | string | 否 | 封面uri，通过sdk上传封面素材后获取。 上传方式见：https://bytedance.larkoffice.com/docx/doxcnyCpq3C9gik15T2dtKK0Tlc?source_type=message&from=message | `tos-cn-i-jm8ajry58r/eef3500af8084b3586c9c15e91c1e89f` |
| `  └ hotspot` | body | string | 否 | 热点 | `小米YU7定价预测` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/publishVideo?app_key=your_appkey_here&method=shopVideo.publishVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `item_id` | mixed | 抖音主端短视频ID | `33322133` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 根据返回文案调整参数 |
| `20000` | 系统错误 / 内部错误（sub_code: isp.service-error:501） | 请尝试重新调用接口 |
| `50002` | 业务处理失败 / 店铺未绑定人店一体账号（sub_code: isv.business-failed:628002009） | 引导商家去抖店-内容-短视频创作tab绑定抖音账号 |

## 响应示例

成功：

```json
{
  "data": {
    "item_id": "33322133"
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
  "sub_code": "isv.parameter-invalid:628002001",
  "sub_msg": "参数错误"
}
```

## 备注
