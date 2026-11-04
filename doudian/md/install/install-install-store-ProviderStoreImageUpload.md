# install.store.ProviderStoreImageUpload

> 服务商门店图片上传接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.install.install.store.ProviderStoreImageUpload` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/ProviderStoreImageUpload` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7676 |
| 更新日期 | `2025-08-05` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `image_url` | body | string | 是 | 公网可以访问的图片链接 | `http://www.czzqp.com/store/b/264513/264513.jpg?20250723160343` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.ProviderStoreImageUpload&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `image_url` | string | 图片链接 | `https://tosv.byted.org/obj/ecom-logistics-YOUR_SECRET_KEY-3755-42b9-822d-d4a78a5588b2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "image_url": "https://tosv.byted.org/obj/ecom-logistics-YOUR_SECRET_KEY-3755-42b9-822d-d4a78a5588b2"
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
