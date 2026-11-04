# 通过前缀匹配召回品牌信息

> brand.getSug — 通过前缀匹配召回品牌信息

| 元信息 | 值 |
| --- | --- |
| 中文名 | 通过前缀匹配召回品牌信息 |
| 文档地址 | `/docs/doudian/product/product-brand-getSug` |
| 接口 ID | `doudian.product.brand.getSug` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/brand/getSug` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/14/1436 |
| 更新日期 | `2021-11-05` |

## 接口说明

- 文档书: 商品API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `query` | body | string | 是 | 前缀匹配的品牌名 | `apple` |
| `user_id` | body | number | 是 | 用户ID，可用默认值0 | `0` |
| `filter_info` | body | object | 否 | 过滤用参数，不填则是全量召回 | `` |
| `  └ brand_ids` | body | array | 否 | 品牌ids | `[202132132342,213123443543]` |
| `  └ brand_category` | body | array | 否 | 品牌类别 | `[20220]` |
| `  └ status` | body | number | 否 | 品牌状态: 1.在线 2.离线 | `1` |
| `  └ related_ids` | body | array | 否 | 品牌商标关联Id | `[12123123123,4323423423]` |
| `  └ trade_mark_ids` | body | array | 否 | 商标IDs | `["21312323134"]` |
| `  └ audit_status` | body | array | 否 | 废弃字段，请勿填写: 1. 审核中 2. 审核通过 3. 审核拒绝 4. 送审失败 | `[2]` |
| `read_old` | body | boolean | 是 | 是否读取老数据 默认为false | `false` |
| `biz_types` | body | array | 是 | 业务线类型: 0. 国内品牌 1. 跨境品牌 3. 广告 | `[0]` |
| `enable_deduplicate` | body | boolean | 是 | 是否去重，一般选择true | `true` |
| `extra_config` | body | object | 否 | 额外配置，无特殊需求请按描述填写 | `` |
| `  └ use_origin_brand_info` | body | boolean | 否 | 是否忽略去重 使用原始品牌信息，默认取false | `false` |
| `  └ use_brand_info` | body | boolean | 否 | 是否忽略新旧映射 使用老品牌信息，默认取false | `false` |
| `  └ use_brand_name_deduplicate` | body | boolean | 否 | 使用品牌名去重，需要和抖店一致请取true | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/brand/getSug?app_key=your_appkey_here&method=brand.getSug&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `sug_list` | array | 品牌信息列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "sug_list": [
      {
        "audit_status": "2",
        "biz_type": "0",
        "brand_alias": "苹果/apple",
        "brand_id": "324234234",
        "brand_name_c_n": "苹果",
        "brand_name_e_n": "apple",
        "create_timestamp": "1636011982",
        "extra": {},
        "level": "0",
        "logo": "url地址",
        "status": "1",
        "update_timestamp": "1636011982"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
