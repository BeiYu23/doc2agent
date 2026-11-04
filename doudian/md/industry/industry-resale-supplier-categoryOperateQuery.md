# 查询旧品类目操作结果

> resale.supplier.categoryOperateQuery — 查询旧品类目操作结果

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询旧品类目操作结果 |
| 文档地址 | `/docs/doudian/industry/industry-resale-supplier-categoryOperateQuery` |
| 接口 ID | `doudian.industry.resale.supplier.categoryOperateQuery` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8464 |
| 更新日期 | `2026-08-12` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `service_entity_code` | body | string | 是 | 服务实体编码 | `SE2024001` |
| `operate_no` | body | string | 是 | 操作编码，服务商自定义，不能重复，用于查询本次操作结果 | `100001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.supplier.categoryOperateQuery&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_msg` | string | 返回消息 | `操作成功` |
| `category_level` | mixed | 类目等级 | `2` |
| `category_detail` | array | 类目详情 | `` |
| `operate_type` | mixed | 操作类型：1：新增，2：修改，3：删除 | `1` |
| `operate_no` | string | 操作编码，服务商自定义，不能重复，用于查询本次操作结果 | `100001` |
| `status` | mixed | 类目状态：1: 已生效 2: 审核中 3: 审核拒绝 | `1` |
| `status_desc` | string | 类目状态描述 | `已生效` |
| `ret_code` | mixed | 返回码 | `0` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "category_detail": [
      {
        "category_id": "C2024001",
        "image_url": "https://example.com/category/image.jpg",
        "level": "2",
        "name": "冰箱",
        "remark": "仅回收100L以上冰箱",
        "sort": "10"
      }
    ],
    "category_level": "2",
    "operate_no": "100001",
    "operate_type": "1",
    "ret_code": "0",
    "ret_msg": "操作成功",
    "status": "1",
    "status_desc": "已生效"
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
