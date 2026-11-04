# 【二方接口】查询登陆信息

> second.shop.getLoginSubjects — 【二方接口】查询登陆信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 【二方接口】查询登陆信息 |
| 文档地址 | `/docs/doudian/dongchedi/dongchedi-second-shop-getLoginSubjects` |
| 接口 ID | `doudian.dongchedi.second.shop.getLoginSubjects` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/shop/getLoginSubjects` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6945 |
| 更新日期 | `2024-10-15` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `loginWay` | body | string | 否 | 登录方式 | `a1420e13` |
| `sysIds` | body | array | 否 | 系统ids | `[]` |
| `busType` | body | array | 否 | 业务类型 | `[]` |
| `loginSource` | body | string | 否 | 登录来源-级别1 | `cd3a6c7d` |
| `oceanId` | body | mixed | 否 | 商业化帐号组uid | `2147563` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/shop/getLoginSubjects?app_key=your_appkey_here&method=second.shop.getLoginSubjects&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `login_subjects` | array | 登录账户列表，可能为空 | `` |
| `retCode` | string | 返回错误码 | `e65d6243` |
| `retStatus` | string | 返回状态 | `fad9ad89` |
| `retMsg` | string | 返回的错误信息 | `58c2736e` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / loginWay不能为空（sub_code: isp.service-error:300001） | loginWay不能为空 |
| `20000` | 系统错误 / sysIds不能为空（sub_code: isp.service-error:300002） | sysIds不能为空 |
| `20000` | 系统错误 / busType不能为空（sub_code: isp.service-error:300003） | busType不能为空 |
| `20000` | 系统错误 / loginSource不能为空（sub_code: isp.service-error:300004） | loginSource不能为空 |
| `20000` | 系统错误 / oceanId不能为空（sub_code: isp.service-error:300005） | oceanId不能为空 |

## 响应示例

成功：

```json
{
  "data": {
    "login_subjects": [
      {
        "bus_id": "6412623",
        "can_not_login": "false",
        "extra": [
          {
            "extra": "dc3fd53c",
            "key": "key"
          }
        ],
        "uid": "2456557"
      }
    ],
    "retCode": "e65d6243",
    "retMsg": "58c2736e",
    "retStatus": "fad9ad89"
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
  "sub_msg": "loginWay不能为空"
}
```

## 备注
