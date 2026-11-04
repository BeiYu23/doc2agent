# 获取叶子类目可选的账号模板id

> topup.accountTemplateList — 获取叶子类目可选的账号模板id

| 元信息 | 值 |
| --- | --- |
| 中文名 | 获取叶子类目可选的账号模板id |
| 文档地址 | `/docs/doudian/virtual/virtual-topup-accountTemplateList` |
| 接口 ID | `doudian.virtual.topup.accountTemplateList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/topup/accountTemplateList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/164/1638 |
| 更新日期 | `2022-01-21` |

## 接口说明

- 文档书: 虚拟充值API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `category_id` | body | number | 是 | 叶子类目id | `21597` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/topup/accountTemplateList?app_key=your_appkey_here&method=topup.accountTemplateList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_list` | array | 模板列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_list": [
      {
        "name": "手机充值",
        "template_id": "1"
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
