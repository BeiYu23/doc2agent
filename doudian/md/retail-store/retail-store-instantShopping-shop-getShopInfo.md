# instantShopping.shop.getShopInfo

> 获取店铺信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.instantShopping.shop.getShopInfo` |
| 中文名 | 获取店铺信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/7377 |
| 更新日期 | `2025-03-23` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| 无参数 | - | - | - | - | - |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.shop.getShopInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shop_user` | object | 即时零售店铺信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40002` | 缺少必选参数 / 参数错误（sub_code: isv.missing-parameter:750003） | 更换参数 |
| `20000` | 系统错误 / 系统异常/店铺信息不存在或已撤销入驻（sub_code: isp.service-error:750001） | 重试； |

## 响应示例

成功：

```json
{
  "data": {
    "shop_user": {
      "instant_retail_info": {
        "enter_type": "1",
        "shop_identity_mode": "1"
      },
      "shop_biz_type": "1"
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
  "code": 40002,
  "msg": "缺少必选参数",
  "sub_code": "isv.missing-parameter:750003",
  "sub_msg": "参数错误"
}
```

## 备注
