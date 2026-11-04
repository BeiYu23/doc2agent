# 创建活动时候可选择的类目

> alliance.activityProductCategoryList — 创建活动时候可选择的类目接口

| 元信息 | 值 |
| --- | --- |
| 中文名 | 创建活动时候可选择的类目 |
| 文档地址 | `/docs/doudian/alliance/alliance-alliance-activityProductCategoryList` |
| 接口 ID | `doudian.alliance.alliance.activityProductCategoryList` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/alliance/activityProductCategoryList` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/61/1882 |
| 更新日期 | `2026-02-27` |

## 接口说明

- 文档书: 精选联盟API（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `channel` | body | mixed | 否 | 类目 0:default 门捷列夫 1:std 标准类目树 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/alliance/activityProductCategoryList?app_key=your_appkey_here&method=alliance.activityProductCategoryList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `category_list` | array | 类目列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 服务打瞌睡了，请稍后再试（sub_code: isp.service-error:256） | 服务打瞌睡了，请稍后再试 |

## 响应示例

成功：

```json
{
  "data": {
    "category_list": [
      {
        "category_id": "111",
        "first_categories": [
          {
            "id": "111111",
            "name": "一级类目名称"
          }
        ],
        "name": "类目一"
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
  "code": 20000,
  "msg": "系统错误",
  "sub_code": "isp.service-error:256",
  "sub_msg": "服务打瞌睡了，请稍后再试"
}
```

## 备注
