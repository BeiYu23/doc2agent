# install.order.supplierSyncSiteInfo

> 服务商同步网点信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.supplierSyncSiteInfo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/supplierSyncSiteInfo` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5779 |
| 更新日期 | `2023-12-21` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operation_no` | body | string | 是 | 实操单号 | `""` |
| `operation_time` | body | string | 是 | 操作时间，格式："yyyy-MM-dd HH:mm:ss" | `""` |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `""` |
| `site_name` | body | string | 否 | 网点名称 | `""` |
| `site_detail_address` | body | string | 否 | 网点地址详情 | `""` |
| `site_latitude` | body | string | 否 | 网点纬度 | `""` |
| `site_longitude` | body | string | 否 | 网点经度 | `""` |
| `site_phone` | body | string | 否 | 网点联系方式，格式，真实号：主机号；虚拟号：主机号-分机号； | `""` |
| `site_contacter_name` | body | string | 否 | 网点联系人姓名 | `""` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=install.order.supplierSyncSiteInfo&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
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
