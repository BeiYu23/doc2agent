# 同步部门员工信息

> instantShopping.logisticsMerchant.syncStaffInfo — 同步部门员工信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 同步部门员工信息 |
| 文档地址 | `/docs/doudian/retail-express/retail-express-instantShopping-logisticsMerchant-syncStaffInfo` |
| 接口 ID | `doudian.retail-express.instantShopping.logisticsMerchant.syncStaffInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1584/7302 |
| 更新日期 | `2025-02-27` |

## 接口说明

- 文档书: 合作快递【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operate_type` | body | mixed | 否 | 操作类型：1-新增，2-修改，3-启用，4-停用，5-删除 | `1` |
| `ext_info` | body | string | 否 | 订单扩展信息，json格式，线下约定不同承运商的kv结构 | `""` |
| `staff_info` | body | object | 否 | 人员信息 | `` |
| `  └ status` | body | mixed | 否 | 人员状态（0-已启用，1-已停用，2-已删除） | `0` |
| `  └ organize_id` | body | string | 否 | 所属组织架构id，不填人员会挂在根节点 | `""` |
| `  └ id` | body | string | 否 | 人员ID | `""` |
| `  └ name` | body | string | 否 | 人员名称 | `""` |
| `  └ phone` | body | string | 否 | 人员手机号，不支持修改 | `""` |
| `role_id` | body | string | 否 | 角色id（范围抖音提供）【功能权限】 | `""` |
| `perm_org_id_list` | body | array | 否 | 有权限的组织架构id列表，不传默认人员所属组织架构【数据权限】 | `[]` |
| `is_test` | body | mixed | 否 | 测试标（0：正式数据，1：测试数据）如未传：测试环境（抖音boe&ppe）默认为测试数据，正式环境默认为正式数据 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.logisticsMerchant.syncStaffInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
