# 行业服务商门店更新门店服务能力

> install.store.providerStoreAPIModifyAbilities — 行业服务商门店更新门店服务能力

| 元信息 | 值 |
| --- | --- |
| 中文名 | 行业服务商门店更新门店服务能力 |
| 文档地址 | `/docs/doudian/install/install-install-store-providerStoreAPIModifyAbilities` |
| 接口 ID | `doudian.install.install.store.providerStoreAPIModifyAbilities` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/store/providerStoreAPIModifyAbilities` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1602/7682 |
| 更新日期 | `2026-02-12` |

## 接口说明

- 文档书: 到店安装API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `op_type` | body | mixed | 否 | 操作类型:0：覆盖式添加。1：增加。2：删除 | `1` |
| `store_id` | body | mixed | 否 | 门店ID | `123` |
| `abilities` | body | array | 否 | 门店能力列表 | `` |
| `  └ ability_id` | body | string | 否 | 能力属性id，注意，这里是key结合的哈 | `34226_304099_7696` |
| `  └ ability_name` | body | string | 否 | 能力属性名称 | `安装刹车片(不含解码)_黄色` |
| `category_channel` | body | mixed | 否 | 类目渠道 | `0表示旧类目体系能力 1表示新类目体系能力` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.store.providerStoreAPIModifyAbilities&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 参数不合法（sub_code: isv.business-failed:-3） | 检查参数重试 |
| `50002` | 业务处理失败 / 门店状态错误，当前状态不可被操作（sub_code: isv.business-failed:-118） | 检查门店状态 |
| `50002` | 业务处理失败 / 获取服务商门店列表失败（sub_code: isv.business-failed:-102） | 重试解决 |
| `50002` | 业务处理失败 / 服务商能力模板获取错误（sub_code: isv.business-failed:-119） | 重试解决 |

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
  "sub_code": "isv.business-failed:-3",
  "sub_msg": "参数不合法"
}
```

## 备注
