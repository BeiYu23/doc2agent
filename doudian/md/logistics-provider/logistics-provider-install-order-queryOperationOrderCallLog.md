# install.order.queryOperationOrderCallLog

> 服务商查询通话记录

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.install.order.queryOperationOrderCallLog` |
| 中文名 | 服务商查询通话记录 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/install/order/queryOperationOrderCallLog` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/5787 |
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

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/product/qualityDetail?app_key=your_appkey_here&method=product.qualityDetail&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `call_log_list` | array | 通话记录 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 10000004:系统内部错误（sub_code: isv.business-failed:10000004） | 10000004:系统内部错误 |

## 响应示例

成功：

```json
{
  "data": {
    "field_problem": [
      {
        "field_key": "product_name",
        "field_name": "标题",
        "problem_key": "501",
        "problem_name": "详情页图片较少",
        "problem_type": "1",
        "suggestion": "商品素材缺少，详情页的图片说明较少。促进商品购买的决策性信息过少，影响购买，建议丰富商品信息，上传不少于5张详情图片，将商品优势展示出来"
      }
    ],
    "product_id": "3469673915587121070",
    "product_name": "奈克牌大皮鞋",
    "quality_score": {
      "level": "lv3",
      "score": "100",
      "version": "middle_score"
    }
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
  "sub_code": "isv.business-failed:10000004",
  "sub_msg": "10000004:系统内部错误"
}
```

## 备注
