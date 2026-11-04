# resale.supplier.quoteResult

> 查询平台生成的询价ID对应的问卷内容

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.logistics-provider.resale.supplier.quoteResult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1048/7737 |
| 更新日期 | `2025-09-02` |

## 接口说明

- 文档书: 物流商API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `quote_id` | body | string | 否 | 询价单id | `13` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=resale.supplier.quoteResult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `quote_json` | string | 问卷结果内容 | `{\"first_category_id\":\"101\",\"second_category_id\":\"10530\",\"third_category_id\":\"58384\",\"opts\":[{\"quote_opt_ids\":[\"1201\"],\"quote_issue_id\":\"1124763\"},{\"quote_opt_ids\":[\"607\"],\"quote_issue_id\":\"1124770\"},{\"quote_opt_ids\":[\"1093559\"],\"quote_issue_id\":\"7191\"},{\"quote_opt_ids\":[\"603\"],\"quote_issue_id\":\"1124769\"},{\"quote_opt_ids\":[\"398228\"],\"quote_issue_id\":\"5587\"},{\"quote_opt_ids\":[\"636\"],\"quote_issue_id\":\"1124764\"},{\"quote_opt_ids\":[\"610\"],\"quote_issue_id\":\"1122122\"},{\"quote_opt_ids\":[\"678741\"],\"quote_issue_id\":\"6651\"},{\"quote_opt_ids\":[\"511435\"],\"quote_issue_id\":\"6652\"},{\"quote_opt_ids\":[\"33684\"],\"quote_issue_id\":\"1224144\"},{\"quote_opt_ids\":[\"615\"],\"quote_issue_id\":\"1124771\"},{\"quote_opt_ids\":[\"595\"],\"quote_issue_id\":\"1124765\"}]}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "quote_json": "{\\\"first_category_id\\\":\\\"101\\\",\\\"second_category_id\\\":\\\"10530\\\",\\\"third_category_id\\\":\\\"58384\\\",\\\"opts\\\":[{\\\"quote_opt_ids\\\":[\\\"1201\\\"],\\\"quote_issue_id\\\":\\\"1124763\\\"},{\\\"quote_opt_ids\\\":[\\\"607\\\"],\\\"quote_issue_id\\\":\\\"1124770\\\"},{\\\"quote_opt_ids\\\":[\\\"1093559\\\"],\\\"quote_issue_id\\\":\\\"7191\\\"},{\\\"quote_opt_ids\\\":[\\\"603\\\"],\\\"quote_issue_id\\\":\\\"1124769\\\"},{\\\"quote_opt_ids\\\":[\\\"398228\\\"],\\\"quote_issue_id\\\":\\\"5587\\\"},{\\\"quote_opt_ids\\\":[\\\"636\\\"],\\\"quote_issue_id\\\":\\\"1124764\\\"},{\\\"quote_opt_ids\\\":[\\\"610\\\"],\\\"quote_issue_id\\\":\\\"1122122\\\"},{\\\"quote_opt_ids\\\":[\\\"678741\\\"],\\\"quote_issue_id\\\":\\\"6651\\\"},{\\\"quote_opt_ids\\\":[\\\"511435\\\"],\\\"quote_issue_id\\\":\\\"6652\\\"},{\\\"quote_opt_ids\\\":[\\\"33684\\\"],\\\"quote_issue_id\\\":\\\"1224144\\\"},{\\\"quote_opt_ids\\\":[\\\"615\\\"],\\\"quote_issue_id\\\":\\\"1124771\\\"},{\\\"quote_opt_ids\\\":[\\\"595\\\"],\\\"quote_issue_id\\\":\\\"1124765\\\"}]}"
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
