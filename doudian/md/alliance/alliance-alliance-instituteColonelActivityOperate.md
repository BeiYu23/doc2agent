# alliance.instituteColonelActivityOperate

> 专属团长活动删除接口（下线+删除）

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.alliance.alliance.instituteColonelActivityOperate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/instituteColonelActivityOperate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/972 |
| 更新日期 | `2022-09-07` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `activity_id` | body | number | 是 | 团长活动id | `11111` |
| `operation` | body | number | 否 | 团长活动状态变更： 1上线，2下线，3删除，4结束报名 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/instituteColonelActivityOperate?app_key=your_appkey_here&method=alliance.instituteColonelActivityOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 活动不是未上线阶段，不能重复上线（sub_code: isv.business-failed:500） | 活动不是未上线阶段，不能重复上线 |
| `50002` | 业务处理失败 / 活动不是未上线阶段，不能上线（sub_code: isv.business-failed:110110） | 活动不是未上线阶段，不能重复上线 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |
| `50002` | 业务处理失败 / 当前用户不是创建活动的用户（sub_code: isv.business-failed:4139） | 当前用户不是创建活动的用户 |
| `50002` | 业务处理失败 / 参数校验失败（sub_code: isv.business-failed:257） | 参数校验失败，请检查 |
| `50002` | 业务处理失败 / 需【招商团长】角色授权后访问（sub_code: isv.business-failed:4197） | 需【招商团长】角色授权后访问 |

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
  "sub_code": "isv.business-failed:500",
  "sub_msg": "活动不是未上线阶段，不能重复上线"
}
```

## 备注
