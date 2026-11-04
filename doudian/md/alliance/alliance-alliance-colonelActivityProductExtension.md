# 专属团长活动商品延时

> alliance.colonelActivityProductExtension — 专属团长活动商品延时接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 专属团长活动商品延时 |
| 文档地址 | `/docs/doudian/alliance/alliance-alliance-colonelActivityProductExtension` |
| 接口 ID | `doudian.alliance.alliance.colonelActivityProductExtension` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/colonelActivityProductExtension` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1881 |
| 更新日期 | `2024-11-22` |

## 接口说明

- 文档书: 精选联盟API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | mixed | 是 | 团长活动id | `111` |
| `product_ids` | body | array | 是 | 商品id 用,隔开,少于20个 | `[3553361443837581161]` |
| `extend_time` | body | string | 是 | 延长的时长 | `2021-09-02` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/colonelActivityProductExtension?app_key=your_appkey_here&method=alliance.colonelActivityProductExtension&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | array | 延迟失败原因列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数校验失败（sub_code: isv.parameter-invalid:257） | 参数校验失败 |
| `50002` | 业务处理失败 / 推广延长时间小于当前时间或小于设置的推广结束时间（sub_code: isv.business-failed:4137） | 请检查延长时间 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |
| `50002` | 业务处理失败 / 活动不是处在报名中，不能审核（sub_code: isv.business-failed:4140） | 活动不是处在报名中，不能审核 |
| `50002` | 业务处理失败 / 当前用户不是创建活动的用户（sub_code: isv.business-failed:4139） | 当前用户不是创建活动的用户 |
| `50002` | 业务处理失败 / 256:服务打瞌睡了，请稍后再试（sub_code: isv.business-failed:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 4200:账号状态异常，请检查账号状态（sub_code: isv.business-failed:4200） | 账号状态异常，请检查账号状态 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "msg": "商品不支持延长推广",
        "product_id": "3553361443837581161"
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
  "sub_code": "isv.parameter-invalid:257",
  "sub_msg": "参数校验失败"
}
```

## 备注
