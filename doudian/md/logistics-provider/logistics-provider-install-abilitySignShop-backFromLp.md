# 服务商商家签约回传

> install.abilitySignShop.backFromLp — 服务商商家签约回传

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商商家签约回传 |
| 文档地址 | `/docs/doudian/logistics-provider/logistics-provider-install-abilitySignShop-backFromLp` |
| 接口 ID | `doudian.logistics-provider.install.abilitySignShop.backFromLp` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5861 |
| 更新日期 | `2023-12-07` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `param` | body | object | 是 | 签约参数对象 | `` |
| `  └ lp_code` | body | string | 是 | 服务商编码（字节提供，固定值，服务商入驻后会生成） | `powerTestCode` |
| `  └ store_id` | body | string | 是 | 店铺ID（店铺唯一标识） | `123452` |
| `  └ res` | body | mixed | 是 | 签约结果 1-同意签约，2-不同意签约 | `1` |
| `  └ remark` | body | string | 否 | 签约说明 | `已完成签约` |
| `  └ event_time` | body | mixed | 是 | 事件时间（秒级时间戳） | `1699522857` |
| `resource_type` | body | string | 是 | 服务商能力类型，HOME_INSTALL_SERVICE：上门安装 | `HOME_INSTALL_SERVICE` |
| `ability_type` | body | string | 是 | 服务商资源类型，INSTALL_SERVICE：安装服务 | `INSTALL_SERVICE` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.abilitySignShop.backFromLp&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 入参对象为空（sub_code: isv.business-failed:-7） | 修正参数，重新调用 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-3） | 修正参数，重新调用 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:-1） | 重试调用 |
| `50002` | 业务处理失败 / 调用RPC异常（sub_code: isv.business-failed:-600） | 重试调用 |

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
  "sub_code": "isv.business-failed:-7",
  "sub_msg": "入参对象为空"
}
```

## 备注
