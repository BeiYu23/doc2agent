# second.category.options

> 【二方接口】获取店铺的可选类目

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.category.options` |
| 中文名 | 【二方接口】获取店铺的可选类目 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/category/options` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6838 |
| 更新日期 | `2024-12-12` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `parentCid` | body | mixed | 否 | 父类目id，获取一级类目，传0 | `1` |
| `filterPersonal` | body | mixed | 否 | 结果是否过滤个人商家不可选类目 | `1` |
| `displayAll` | body | mixed | 否 | 是否展示所有类目 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/second/category/options?app_key=your_appkey_here&method=second.category.options&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `categoryList` | array | 查询结果 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:300002） | shopId不能为空 |
| `20000` | 系统错误 / parentCid参数非法（sub_code: isp.service-error:300003） | parentCid参数非法 |

## 响应示例

成功：

```json
{
  "data": {
    "categoryList": [
      {
        "id": "1",
        "isLeaf": "1",
        "level": "level",
        "name": "test"
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
  "sub_code": "isp.service-error:300002",
  "sub_msg": "shopId不能为空"
}
```

## 备注
