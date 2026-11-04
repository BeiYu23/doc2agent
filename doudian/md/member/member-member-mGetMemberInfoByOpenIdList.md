# member.mGetMemberInfoByOpenIdList

> 【会员通商家】获取会员信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.mGetMemberInfoByOpenIdList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/mGetMemberInfoByOpenIdList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/2750 |
| 更新日期 | `2024-11-20` |

## 接口说明

- 文档书: 会员中心API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `app_id` | body | mixed | 是 | 表明外部平台 | `1` |
| `open_id_list` | body | array | 是 | 会员对外的OpenID列表 | `["openIdopenIdopenIdopenIdopenId1","openIdopenIdopenIdopenIdopenId2"]` |
| `extend_info_list` | body | array | 否 | 额外补充信息 | `` |
| `  └ open_id` | body | string | 否 | 同open_id_list中的open_id，对open_id_list中的open_id在查询时补充其他信息 | `"openIdopenIdopenIdopenIdopenId1"` |
| `  └ mask_mobile` | body | string | 否 | 使用手机号掩码查询 | `"***4567****"` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/member/mGetMemberInfoByOpenIdList?app_key=your_appkey_here&method=member.mGetMemberInfoByOpenIdList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `member_infos` | array | 获取到的会员信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 网络错误，请稍后再试~（sub_code: isp.service-error:628145000） | 请稍后重试 |
| `40004` | 非法的参数 / [OpenIdList]长度不能大于10（sub_code: isv.parameter-invalid:628002001） | 请检查请求的入参 |
| `60000` | 触发限流，请稍后重试 / 请求过于频繁（sub_code: isp.traffic-limited:628002006） | 请求过于频繁，请稍后重试 |
| `50002` | 业务处理失败 / 商家未开通会员体系（sub_code: isv.business-failed:628005200） | 请商家联系产运开通会员体系 |
| `50002` | 业务处理失败 / 非会员通店铺不支持获取会员信息（sub_code: isv.business-failed:628145011） | 请商家联系产运开通会员通 |
| `40004` | 非法的参数 / openId非法（sub_code: isv.parameter-invalid:628145003） | 请检查openId是否填写正确或者是否是本店铺用户 |
| `50002` | 业务处理失败 / 用户不是当前店铺的会员（sub_code: isv.business-failed:628145004） | 引导用户加入成为本店铺的会员 |
| `50002` | 业务处理失败 / 会员信息错误（sub_code: isv.business-failed:628145012） | 请更新会员数据 |
| `50002` | 业务处理失败 / 店铺未绑定会员通应用（sub_code: isv.business-failed:628145008） | 请绑定会员通应用 |
| `50002` | 业务处理失败 / 内部处理失败，请稍后重试~（sub_code: isv.business-failed:628145042） | 请稍后重试 |
| `50002` | 业务处理失败 / 请求超时，请稍后重试（sub_code: isv.business-failed:628004002） | 请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "member_infos": [
      {
        "err_code": "628145000",
        "err_msg": "网络错误，请稍后再试~",
        "extend": "{\"xxx\":\"xx\"}",
        "level": "1",
        "mask_mobile": "123****8901",
        "mix_mobile": "9RKZFZxfHu4mQiKl_4lskxIZtjxYh4RBV2QqrrBs1rA=",
        "mobile": "18888888888",
        "open_id": "1@#Y87HxmsBxAuJxfgyGhC4u435kyRrL8VToh8DZ0UT46MMARbJgAcV5bcL3g==",
        "point_cent": "100",
        "success": "true",
        "union_id": "1@#Y87HxmsBxAuJxfgyGhC4u435kyRrL8VToh8DZ0UT46MMARbJgAcV5bcL3g=="
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
