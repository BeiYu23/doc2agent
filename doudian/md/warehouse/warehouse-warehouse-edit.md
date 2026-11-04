# warehouse.edit

> 编辑区域仓

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.warehouse.warehouse.edit` |
| 中文名 | 编辑区域仓 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/warehouse/edit` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/50/2078 |
| 更新日期 | `2022-06-23` |

## 接口说明

- 文档书: 仓库作业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `out_warehouse_id` | body | string | 是 | 外部仓库id | `abc` |
| `name` | body | string | 否 | 仓库名称 | `仓名称示例` |
| `intro` | body | string | 否 | 仓库介绍 | `仓介绍示例` |
| `address_id1` | body | number | 否 | 省地址编码 | `11` |
| `address_id2` | body | number | 否 | 市地址编码 | `110000` |
| `address_id3` | body | number | 否 | 区地址编码 | `110101` |
| `address_id4` | body | number | 否 | 街道地址编码 | `0` |
| `address_detail` | body | string | 否 | 详细地址 | `xx消息xx号` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/warehouse/edit?app_key=your_appkey_here&method=warehouse.edit&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `data` | boolean | 修改结果 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": "true"
  },
  "err_no": 0,
  "message": "success",
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
