# mini.fans.userInfo

> 获取用户的购物粉丝团等级

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.fans.userInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/fans/userInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/6932 |
| 更新日期 | `2024-10-18` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `author_id` | body | mixed | 是 | 达人uid | `20497802913801293` |
| `dy_open_id` | body | string | 是 | c端用户抖音openId | `fdhiejoadsf_912070213` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/buyin/materialsProductStatus?app_key=your_appkey_here&method=buyin.materialsProductStatus&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `intimacy` | mixed | 亲密度 | `1000` |
| `level` | mixed | 亲密度等级 | `2` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 606010000:入参UserId非法（sub_code: isv.business-failed:606010000） | 传用户抖音openid |
| `50002` | 业务处理失败 / 606000102:RPCError{PSM:[ecom.fans.club] Method:[MGetUserFansInfo] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS\|cmp.ecom.open_trade:default:lf:\|ecom.fans.club:default::\|MGetUserFansInfo\|prod\| reas（sub_code: isv.business-failed:606000102） | 606000102:RPCError{PSM:[ecom.fans.club] Method:[MGetUserFansInfo] ErrType:[RPC_FAILED] OriginalErr:[remote or network error[remote]: error_code=1204 cds_key=THRIFT_EGRESS\|cmp.ecom.open_trade:default:lf:\|ecom.fans.club:default::\|MGetUserFansInfo\|prod\| reas |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "can_share": "true",
        "join_alliance": "true",
        "product_url": "https://haohuo.jinritemai.com/views/product/detail?id=798754293457134",
        "promotion_status": "2",
        "status": "0"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:606010000",
  "sub_msg": "606010000:入参UserId非法"
}
```

## 备注
