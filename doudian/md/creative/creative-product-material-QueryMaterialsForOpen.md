# 查询作品素材信息

> product.material.QueryMaterialsForOpen — 查询作品素材信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询作品素材信息 |
| 文档地址 | `/docs/doudian/creative/creative-product-material-QueryMaterialsForOpen` |
| 接口 ID | `doudian.creative.product.material.QueryMaterialsForOpen` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4256 |
| 更新日期 | `2023-08-03` |

## 接口说明

- 文档书: 创意管理API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_ids` | body | array | 否 | 商品id列表 | `[1111,222,333]` |
| `material_types` | body | array | 否 | 素材类型 0-主图视频 1-白底图 | `[0,1]` |
| `material_status` | body | array | 否 | 素材状态 -1:已删除 0:待发布 1:审核中 2:已上线 3:审核未通过 | `[0,1]` |
| `material_ids` | body | array | 否 | 作品素材id列表 | `[111,333,222]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=product.material.QueryMaterialsForOpen&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `materials` | array | 作品素材列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 素材查询异常（sub_code: isv.business-failed:20121019） | 联系或者重试 |
| `40004` | 非法的参数 / 无效入参（sub_code: isv.parameter-invalid:2012004） | 请重新校验入参 |
| `20000` | 系统错误（sub_code: isp.service-error:2012001） | 联系或者重试 |

## 响应示例

成功：

```json
{
  "data": {
    "materials": [
      {
        "audit_time": "1690510680",
        "create_time": "1690510680",
        "material_id": "1231",
        "material_status": "1",
        "material_type": "0",
        "product_id": "12323",
        "reject_reason": "不过关",
        "shop_id": "123",
        "update_time": "1690510680"
      }
    ]
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
  "sub_code": "isv.business-failed:20121019",
  "sub_msg": "素材查询异常"
}
```

## 备注
