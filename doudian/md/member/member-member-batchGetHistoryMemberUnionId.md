# member.batchGetHistoryMemberUnionId

> 该接口可以根据店铺会员的openId获取品牌维度的用户身份标识unionId。同品牌下跨店铺中存量的抖音会员，可以用这个接口查询unionId，相同的unionId表示是同一个用户。
注1：店铺如果不是品牌店铺，将无法获取unionId
注2：用户如果不是

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.batchGetHistoryMemberUnionId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/batchGetHistoryMemberUnionId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/2136 |
| 更新日期 | `2022-07-01` |

## 接口说明

- 文档书: 会员中心API（版本 V1.02）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `app_id` | body | number | 是 | 表明外部平台 | `1` |
| `open_id_list` | body | array | 是 | 会员对外的OpenID列表，该接口一次最多进行20个Openld的解析 | `["openIdopenIdopenIdopenIdopenId1","openIdopenIdopenIdopenIdopenId2"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/batchGetHistoryMemberUnionId?app_key=your_appkey_here&method=member.batchGetHistoryMemberUnionId&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `union_id_infos` | array | 获取到的unionId列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 网络错误，请稍后再试~（sub_code: isp.service-error:628145000） | 请稍后重试 |
| `50002` | 业务处理失败 / 非品牌会员店铺不支持获取UnionId（sub_code: isv.business-failed:628145001） | 品牌方到抖店企业版中圈选本店铺为品牌店铺 |
| `50002` | 业务处理失败 / 非会员通店铺不支持获取UnionId（sub_code: isv.business-failed:628145002） | 请联系平台运营提报并开通会员通体系 |
| `40004` | 非法的参数 / openId非法（sub_code: isv.parameter-invalid:628145003） | 请检查openId是否填写正确或者是否是本店铺用户 |
| `50002` | 业务处理失败 / 用户不是当前店铺的会员（sub_code: isv.business-failed:628145004） | 用户加入成为本店铺的会员 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:628002001） | 请检查请求的入参 |
| `60000` | 触发限流，请稍后重试 / 请求过于频繁（sub_code: isp.traffic-limited:628002006） | 请求过于频繁，请稍后重试 |
| `50002` | 业务处理失败 / 商家未开通会员体系（sub_code: isv.business-failed:628005200） | 请商家联系产运开通会员体系 |

## 响应示例

成功：

```json
{
  "data": {
    "union_id_infos": [
      {
        "err_code": "628145000",
        "err_msg": "网络错误，请稍后再试~",
        "open_id": "openIdopenIdstring",
        "success": "true",
        "union_id": "unionIdunionIdstring"
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
  "sub_code": "isp.service-error:628145000",
  "sub_msg": "网络错误，请稍后再试~"
}
```

## 备注
