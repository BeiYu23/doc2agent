# 服务商推送旧品类目变更

> resale.supplier.categoryOperate — 服务商推送旧品类目变更

| 元信息 | 值 |
| --- | --- |
| 中文名 | 服务商推送旧品类目变更 |
| 文档地址 | `/docs/doudian/industry/industry-resale-supplier-categoryOperate` |
| 接口 ID | `doudian.industry.resale.supplier.categoryOperate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8466 |
| 更新日期 | `2026-08-12` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operate_type` | body | mixed | 是 | 操作类型：1：新增，2：修改，3：删除 | `1` |
| `operate_no` | body | string | 是 | 操作编码，服务商自定义，不能重复，用于查询本次操作结果 | `100001` |
| `service_entity_code` | body | string | 是 | 服务实体编码,对接时找平台研发确认 | `SE20240520001` |
| `category_level` | body | mixed | 否 | 类目等级 | `3` |
| `category_detail` | body | array | 否 | 类目详情 | `` |
| `  └ sort` | body | mixed | 否 | 类目排序 | `10` |
| `  └ level` | body | mixed | 否 | 类目层级 | `1` |
| `  └ name` | body | string | 否 | 类目名称 | `家用冰箱` |
| `  └ remark` | body | string | 否 | 类目描述 (部分叶子类目，回收备注,比如大家电可能需要限制仅回收100L以上冰箱) | `仅回收100L以上冰箱` |
| `  └ category_id` | body | string | 否 | 类目编码 | `C2024001` |
| `  └ image_url` | body | string | 否 | 类目图片 | `https://example.com/category_image.jpg` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.supplier.categoryOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_code` | mixed | 返回码,0 代表受理成功，其它为异常，原因参考ret_msg | `0` |
| `ret_msg` | string | 返回码描述 | `操作成功` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "ret_code": "0",
    "ret_msg": "操作成功"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
