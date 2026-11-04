# second.category.getFullItemsByIds

> 【二方接口】根据类目ID查询本级类目信息

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.category.getFullItemsByIds` |
| 中文名 | 【二方接口】根据类目ID查询本级类目信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/6839 |
| 更新日期 | `2024-09-03` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `ids` | body | array | 否 | ids | `[1001]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.category.getFullItemsByIds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `items` | array | 当前节点信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / ids不能为空（sub_code: isp.service-error:300001） | ids不能为空 |

## 响应示例

成功：

```json
{
  "data": {
    "items": [
      {
        "auditStatus": "1",
        "bizSourceInfoList": [
          {
            "bizSource": "1",
            "desc": "test",
            "name": "test"
          }
        ],
        "createTime": "1",
        "description": "test",
        "id": "1",
        "isLeaf": "true",
        "level": "1",
        "name": "test",
        "opType": "1",
        "parentId": "1",
        "parentInfos": [
          {
            "key": "1001",
            "value": {
              "auditStatus": "1",
              "bizSourceInfoList": [
                {
                  "bizSource": "1",
                  "desc": "test",
                  "name": "test"
                }
              ],
              "createTime": "1",
              "description": "test",
              "id": "1",
              "isLeaf": "false",
              "level": "1",
              "name": "test",
              "opType": "1",
              "parentId": "1",
              "sequence": "1",
              "status": "1",
              "updateTime": "1"
            }
          }
        ],
        "sequence": "1",
        "status": "1",
        "updateTime": "1"
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
  "sub_code": "isp.service-error:300001",
  "sub_msg": "ids不能为空"
}
```

## 备注
