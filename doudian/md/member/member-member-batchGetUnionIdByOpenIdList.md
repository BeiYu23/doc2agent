# 会员open_id转union_id

> member.batchGetUnionIdByOpenIdList — 会员open_id转union_id

| 元信息 | 值 |
| --- | --- |
| 中文名 | 会员open_id转union_id |
| 文档地址 | `/docs/doudian/member/member-member-batchGetUnionIdByOpenIdList` |
| 接口 ID | `doudian.member.member.batchGetUnionIdByOpenIdList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/batchGetUnionIdByOpenIdList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/1790 |
| 更新日期 | `2023-04-17` |

## 接口说明

- 文档书: 会员中心API（版本 V1.09）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `app_id` | body | number | 是 | 表明外部平台 | `1` |
| `open_id_list` | body | array | 是 | 会员对外的OpenID列表 | `["1@#YOUR_SECRET_KEY"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `union_id_info` | string | 返回传入的OpenID对应的UnionID map中的key是请求的OpenId，value是OpenId对应的UnionId | `{"1@#YOUR_SECRET_KEY": "1@#YOUR_SECRET_KEY"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -100001:请求参数非法（sub_code: isv.business-failed:-100001） | 检查接口请求参数是否有误 |
| `20000` | 系统错误 / -100002:网络错误（sub_code: isp.service-error:-100002） | 请稍后重试 |
| `50002` | 业务处理失败 / 628002001:会员店铺不存在（sub_code: isv.business-failed:628002001） | 请检查自用型应用的店铺是否开通了会员通功能 |
| `50002` | 业务处理失败 / 628145000:网络错误，请稍后再试~（sub_code: isv.business-failed:628145000） | 请稍后重试 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:-100001",
  "sub_msg": "-100001:请求参数非法"
}
```

## 备注
