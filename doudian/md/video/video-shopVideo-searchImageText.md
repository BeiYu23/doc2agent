# shopVideo.searchImageText

> 搜索图文

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.searchImageText` |
| 中文名 | 搜索图文 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/searchImageText` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/8141 |
| 更新日期 | `2026-03-13` |

## 接口说明

- 文档书: 短视频API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | string | 否 | 作者账号id | `11` |
| `item_id` | body | string | 否 | 图文id | `1` |
| `page` | body | string | 否 | 页码 | `1` |
| `page_size` | body | string | 否 | 每页数量，默认10 | `1` |
| `product` | body | object | 否 | 商品参数（使用商品id查询时，必传bind_scene，否则商品过滤无效） | `` |
| `  └ product_id` | body | string | 否 | 商品id | `123443` |
| `bind_scene` | body | string | 否 | 商品绑定场景（传入productId时，该参数必传，否则商品过滤无效）  1:只查挂车图文 2:查询所有非挂车图文 3:查询所有未绑定商品图文 4:全部 | `4` |
| `status` | body | string | 否 | 图文发布状态：22-用户删除，23-审核删除，102-公开，140-支持运营、用户并行审核流程，141-待审/自见，142-需要编辑终审，143-好友可见，144-审核自见 | `102` |
| `optional_param` | body | object | 否 | 可选查询参数 | `` |
| `  └ need_product_info` | body | boolean | 否 | 是否需要商品信息，挂车或看后搜 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | 数据 | `` |
| `total` | number | 总数 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:1000001） | 检查输入参数 |

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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:1000001",
  "sub_msg": "参数错误"
}
```

## 备注
