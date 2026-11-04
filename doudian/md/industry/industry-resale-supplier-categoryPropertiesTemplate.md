# resale.supplier.categoryPropertiesTemplate

> 推送叶子类目对应的类目属性和模版

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.industry.resale.supplier.categoryPropertiesTemplate` |
| 中文名 | 推送叶子类目对应的类目属性和模版 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1612/8465 |
| 更新日期 | `2026-08-06` |

## 接口说明

- 文档书: 行业API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_properties` | body | object | 否 | 类目属性 | `` |
| `  └ max_price` | body | mixed | 否 | 最高回收价 | `5000` |
| `  └ pct50_price` | body | mixed | 否 | 中位数回收价 | `3000` |
| `  └ support_modes` | body | array | 否 | 支持的回收模式，不传默认为分离式，[0]:分离式，都支持：传入[0,1] | `[0]` |
| `  └ hot_sort` | body | string | 否 | 热门排序 | `sales_desc` |
| `first_category_id` | body | string | 否 | 一级类目编码 | `1001` |
| `second_category_id` | body | string | 否 | 二级类目编码 | `10010001` |
| `ability_cate_issues` | body | array | 否 | 模板问题 | `` |
| `  └ issue_tips` | body | array | 否 | 问题提示 | `` |
| `    └ tip_img` | body | string | 否 | 提示图片 | `https://example.com/tip1.jpg` |
| `    └ tip_desc` | body | string | 否 | 提示描述 | `请描述划痕的位置和长度` |
| `  └ issue_desc` | body | string | 否 | 问题描述 | `屏幕是否有划痕` |
| `  └ opts` | body | array | 否 | 选项 | `` |
| `    └ can_save` | body | mixed | 否 | 是否可保存 | `true` |
| `    └ disable` | body | mixed | 否 | 是否禁用 | `false` |
| `    └ opt_tips` | body | array | 否 | 选项提示 | `` |
| `      └ tip_img` | body | string | 否 | 提示图片 | `https://example.com/opt1.jpg` |
| `      └ tip_desc` | body | string | 否 | 提示描述 | `不影响正常使用` |
| `    └ notice_tips` | body | array | 否 | 选项提示 | `` |
| `      └ tip_desc` | body | string | 否 | 提示描述 | `此选项将影响回收价格` |
| `      └ tip_img` | body | string | 否 | 提示图片 | `https://example.com/notice1.jpg` |
| `    └ quote_opt_id` | body | string | 否 | 选项id | `opt_001` |
| `    └ opt_desc` | body | string | 否 | 选项描述 | `轻微划痕` |
| `  └ need` | body | mixed | 否 | 是否必填 | `true` |
| `  └ quote_issue_id` | body | string | 否 | 问卷id | `q_123456` |
| `  └ multi` | body | mixed | 否 | 是否多选 | `true` |
| `service_entity_code` | body | string | 否 | 服务实体编码 | `SE_001` |
| `third_category_id` | body | string | 否 | 三级类目编码 | `100100010001` |
| `fourth_category_id` | body | string | 否 | 四级类目编码 | `100100010001` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.supplier.categoryPropertiesTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `ret_code` | mixed | 返回码 | `0` |
| `ret_msg` | string | 返回消息 | `success` |

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
    "ret_msg": "success"
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
