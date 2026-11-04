# mini.follow.check

> 检查小程序是否允许关注店铺

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.miniapp.mini.follow.check` |
| 中文名 | 检查小程序是否允许关注店铺 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/mini/follow/check` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1434/5083 |
| 更新日期 | `2023-11-06` |

## 接口说明

- 文档书: 电商小程序（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `follow_shop_id` | body | number | 否 | 待关注的店铺ID，如不填写会使用当前小程序绑定的店铺ID | `77977` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/mini/follow/check?app_key=your_appkey_here&method=mini.follow.check&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `bc_check_success` | boolean | 关系检查正常 | `true` |
| `shop_uid` | string | 店铺uid | `8213121232` |
| `follow_result` | boolean | 是否已关注 | `false` |
| `aweme_id` | string | 抖音号ID | `123123123` |
| `aweme_nick` | string | 抖音号昵称 | `vda112` |
| `avatar` | string | 抖音头像 | `https://p11.douyinpic.com/img/aweme-avatar/tos-cn-avt-0015_6f08413fa71c50856524d20e8ca76dd6~c5_300x300.jpeg?from=3782654143` |
| `shop_name` | string | 店铺名称 | `vda112` |
| `shop_score` | string | 店铺评分 | `4.99` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 当前店铺没有绑定小程序，请检查（sub_code: isv.business-failed:605014001） | 当前店铺没有绑定小程序，请检查 |
| `50002` | 业务处理失败 / 店铺信息查询异常，请稍后重试（sub_code: isv.business-failed:605014002） | 店铺信息查询异常，请稍后重试 |
| `20000` | 系统错误 / 服务异常，请稍后重试（sub_code: isp.service-error:605090001） | 服务异常，请稍后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "avatar": "https://p11.douyinpic.com/img/aweme-avatar/tos-cn-avt-0015_6f08413fa71c50856524d20e8ca76dd6~c5_300x300.jpeg?from=3782654143",
    "aweme_id": "123123123",
    "aweme_nick": "vda112",
    "bc_check_success": "true",
    "follow_result": "false",
    "shop_name": "vda112",
    "shop_score": "4.99",
    "shop_uid": "8213121232"
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
  "sub_code": "isv.business-failed:605014001",
  "sub_msg": "当前店铺没有绑定小程序，请检查"
}
```

## 备注
