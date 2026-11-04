# 查询店铺下所有账号信息

> shopVideo.getShopAccountInfo — 查询店铺下所有账号信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询店铺下所有账号信息 |
| 文档地址 | `/docs/doudian/video/video-shopVideo-getShopAccountInfo` |
| 接口 ID | `doudian.video.shopVideo.getShopAccountInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shopVideo/getShopAccountInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1568/7490 |
| 更新日期 | `2025-05-28` |

## 接口说明

- 文档书: 短视频API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shopVideo/getShopAccountInfo?app_key=your_appkey_here&method=shopVideo.getShopAccountInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `account_infos` | array | 账户信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "account_infos": [
      {
        "avatar_url": "https://2222",
        "type": "1",
        "user_id": "1221212",
        "user_name": "我是名字"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
