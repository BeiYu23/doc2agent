# second.category.pageQueryCatOperationCategory

> 【二方接口】分页获取垂类类目信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.category.pageQueryCatOperationCategory` |
| 中文名 | 【二方接口】分页获取垂类类目信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6837 |
| 更新日期 | `2026-02-25` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `enumIds` | body | array | 否 | 垂类枚举 | `1` |
| `pageNo` | body | mixed | 否 | 页码，第一页从0开始 | `0` |
| `pageSize` | body | mixed | 否 | 分页大小 | `20` |
| `channel` | body | mixed | 否 | 类目 0:default 门捷列夫 1:std 标准类目树 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.category.pageQueryCatOperationCategory&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `categoryTags` | array | 属性信息 | `` |
| `total` | mixed | 总数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / 参数pageNo非法（sub_code: isp.service-error:300001） | 参数pageNo非法 |
| `20000` | 系统错误 / 参数pageSize非法（sub_code: isp.service-error:300002） | 参数pageSize非法 |

## 响应示例

成功：

```json
{
  "data": {
    "categoryTags": [
      {
        "categoryId": "1",
        "tagEnumId": "1",
        "tagEnumName": "test"
      }
    ],
    "total": "10"
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
  "sub_code": "isp.service-error:300001",
  "sub_msg": "参数pageNo非法"
}
```

## 备注
