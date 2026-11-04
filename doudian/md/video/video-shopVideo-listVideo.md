# shopVideo.listVideo

> 查询已投稿短视频列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.listVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/listVideo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7146 |
| 更新日期 | `2024-12-12` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `create_time_start` | body | mixed | 否 | 视频上传开始时间戳，支持查询90天内视频 | `1733910301` |
| `page` | body | mixed | 是 | 页码，>1 | `1` |
| `size` | body | mixed | 是 | 每页数量，1至50 | `20` |
| `order_by_type` | body | mixed | 否 | 排序类型：0-降序，1-升序 | `0` |
| `item_id` | body | mixed | 否 | 抖音主端短视频ID | `2344` |
| `order_by_field` | body | mixed | 否 | 排序字段，1-创建时间，2-累计成交量，3-播放量 | `1` |
| `bind_product_id` | body | mixed | 否 | 关联的商品id | `22333` |
| `bind_type_list` | body | array | 否 | 绑定类型：0-未绑定，1-挂车，2-种草 | `2` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/listVideo?app_key=your_appkey_here&method=shopVideo.listVideo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `video_list` | array | 视频列表 | `` |
| `total` | mixed | 总数 | `99` |
| `current_page` | mixed | 当前页码 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:628002001） | 根据异常描述调整参数 |

## 响应示例

成功：

```json
{
  "data": {
    "current_page": "1",
    "total": "99",
    "video_list": [
      {
        "alliance_product_list": "[2233]",
        "bind_type": "2",
        "create_time": "1733910689",
        "item_id": "232323",
        "modify_time": "1733910689",
        "order_amount": "290",
        "play_count": "100",
        "seeding_product_list": "[333]",
        "shop_id": "232323",
        "status": "0",
        "user_id": "2323"
      }
    ]
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
