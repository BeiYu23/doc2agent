# topup.productActionCUC

> 商品上下架接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.virtual.topup.productActionCUC` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/productActionCUC` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/7984 |
| 更新日期 | `2025-12-25` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `goodCode` | body | string | 否 | 商品编码，固定传 DYSC_CUC | `1` |
| `actionType` | body | string | 否 | 1-上架，2-下架 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/JoinShopMemberWithMobileId?app_key=your_appkey_here&method=member.JoinShopMemberWithMobileId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `returnCode` | string | 返回码：0-成功，其他-失败 | `0` |
| `message` | string | 返回信息 | `1` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
