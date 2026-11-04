# second.shop.getShopInfo

> 【二方接口】查询店铺信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.shop.getShopInfo` |
| 中文名 | 【二方接口】查询店铺信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/shop/getShopInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6944 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `shopIds` | body | array | 否 | 最多20个店铺 | `[]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/shop/getShopInfo?app_key=your_appkey_here&method=second.shop.getShopInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `shopInfoList` | array | shop_info_list | `[]` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / shopIds不能为空（sub_code: isp.service-error:300001） | shopIds不能为空 |

## 响应示例

成功：

```json
{
  "data": {
    "shopInfoList": [
      {
        "encryptShopId": "4b19be0b",
        "id": "1891118",
        "shopName": "ecdb7c5d"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:300001",
  "sub_msg": "shopIds不能为空"
}
```

## 备注
