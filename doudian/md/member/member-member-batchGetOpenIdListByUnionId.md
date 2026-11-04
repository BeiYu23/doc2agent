# member.batchGetOpenIdListByUnionId

> 服务商可以根据品牌维度的用户唯一身份UnionId来查询品牌下每个店铺的用户OpenId

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.member.member.batchGetOpenIdListByUnionId` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/member/batchGetOpenIdListByUnionId` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/66/2814 |
| 更新日期 | `2022-12-08` |

## 接口说明

- 文档书: 会员中心API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `union_id_list` | body | array | 是 | 注意： 1）该接口一次最多进行10个UnionId的解析。 2）任意一个unionId不合法都可能导致整个批量请求失败，请传入正确的unionId | `["1@#YOUR_SECRET_KEY","1@#YOUR_SECRET_KEY"]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.comtest/encrypt/2?app_key=your_appkey_here&method=test.encrypt.2&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `open_ids_info_list` | array | 返回的结果列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / UnionId非法，无法正常解析（sub_code: isv.parameter-invalid:628145021） | 请确保传入的unionId数据准确 且 和当前店铺有关联 |
| `50002` | 业务处理失败 / 用户不是当前店铺的会员或者会员已解绑（sub_code: isv.business-failed:628145022） | 仅允许当前店铺品牌会员的unionId来查询 |
| `50002` | 业务处理失败 / 请求的店铺非品牌店铺（sub_code: isv.business-failed:628145023） | 请确保请求店铺是品牌店铺 |
| `50002` | 业务处理失败 / 商家未开通会员体系（sub_code: isv.business-failed:628005200） | 请确保请求店铺已开通会员体系 |
| `50002` | 业务处理失败 / 628145000:网络错误，请稍后再试~（sub_code: isv.business-failed:628145000） | 628145000:网络错误，请稍后再试~ |

## 响应示例

成功：

```json
{
  "data": {
    "data": "2",
    "or": "7"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:628145021",
  "sub_msg": "UnionId非法，无法正常解析"
}
```

## 备注
