# 同步组织架构

> instantShopping.logisticsMerchant.syncOrganizeStructure — 同步组织架构

| 元信息 | 值 |
| --- | --- |
| 中文名 | 同步组织架构 |
| 文档地址 | `/docs/doudian/retail-express/retail-express-instantShopping-logisticsMerchant-syncOrganizeStructure` |
| 接口 ID | `doudian.retail-express.instantShopping.logisticsMerchant.syncOrganizeStructure` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1584/7303 |
| 更新日期 | `2025-02-27` |

## 接口说明

- 文档书: 合作快递【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `organize_id` | body | string | 否 | 组织架构id | `""` |
| `organize_code` | body | string | 否 | 组织架构code，为网点时必传 | `""` |
| `organize_name` | body | string | 否 | 组织架构名称 | `""` |
| `organize_type` | body | mixed | 否 | 组织架构类型：1-网点，2-普通部门 | `1` |
| `parent_organize_id` | body | string | 否 | 需归属的上级组织架构id，为空默认挂载在根组织架构上 | `""` |
| `operate_type` | body | mixed | 否 | 操作类型：1-新增，2-修改，3-删除 | `1` |
| `ext_info` | body | string | 否 | 订单扩展信息，json格式，线下约定不同承运商的kv结构 | `""` |
| `is_test` | body | mixed | 否 | 测试标（0：正式数据，1：测试数据）如未传：测试环境（抖音boe&ppe）默认为测试数据，正式环境默认为正式数据 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logisticsMerchant.syncOrganizeStructure&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
