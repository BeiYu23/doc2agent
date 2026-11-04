# 服务商回传货主状态

> instantShopping.syncGoodsOwnerStatus — 服务商回传货主状态

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商回传货主状态 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-instantShopping-syncGoodsOwnerStatus` |
| 接口 ID | `doudian.logistics-provider.instantShopping.syncGoodsOwnerStatus` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7022 |
| 更新日期 | `2024-10-23` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `org_shop_id` | body | string | 是 | 抖音货主id | `21314` |
| `outer_shop_id` | body | string | 是 | 服务商货主id | `21314` |
| `status` | body | mixed | 是 | 状态 1-完成 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.syncGoodsOwnerStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:40001） | 传入合法入参 |

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
  "sub_code": "isv.parameter-invalid:40001",
  "sub_msg": "参数错误"
}
```

## 备注
