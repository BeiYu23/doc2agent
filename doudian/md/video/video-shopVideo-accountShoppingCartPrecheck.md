# shopVideo.accountShoppingCartPrecheck

> 挂车视频预校验接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.video.shopVideo.accountShoppingCartPrecheck` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/accountShoppingCartPrecheck` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7477 |
| 更新日期 | `2026-03-11` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `user_id` | body | string | 否 | 账号ID，支持获取授权号信息 | `123456` |
| `content_type` | body | string | 否 | 体裁类型：video-视频（默认），image-图文 | `video` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/accountShoppingCartPrecheck?app_key=your_appkey_here&method=shopVideo.accountShoppingCartPrecheck&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | object | data | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": {
      "can_bind": "true",
      "deposit_paid": "true",
      "remain_bind_num": "1"
    }
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
