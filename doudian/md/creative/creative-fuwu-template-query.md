# 查询模板服务列表

> fuwu.template.query — 查询模板服务列表

| 元信息 | 值 |
| --- | --- |
| 中文名 | 查询模板服务列表 |
| 文档地址 | `/docs/doudian/creative/creative-fuwu-template-query` |
| 接口 ID | `doudian.creative.fuwu.template.query` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/template/query` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4201 |
| 更新日期 | `2023-08-04` |

## 接口说明

- 文档书: 创意管理API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_no` | body | string | 否 | 起始页(从1开始) | `1` |
| `page_size` | body | string | 否 | 页大小(0～100) | `10` |
| `status_list` | body | array | 否 | 服务状态：-2删除，-1初始化，0上架，1 审核中, 2下架， | `[0]` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/template/query?app_key=your_appkey_here&method=fuwu.template.query&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `template_list` | array | 模板列表 | `` |
| `total` | number | 总条数 | `10` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:100001） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "template_list": [
      {
        "labels": "[1,2]",
        "preview_info": {
          "picture_paths": "['1.jpeg']",
          "thumbnail": "cover.jpg",
          "video_path": "xxx.mp4"
        },
        "service_id": "111111",
        "service_type": "1",
        "skus": [
          {
            "duration_id": "6",
            "price": "100",
            "price_type": "0"
          }
        ],
        "status": "0",
        "suite_industry": {
          "industry_ids": "[123]",
          "suite_type": "2"
        },
        "template_code": "111111",
        "template_info": {
          "displaying_text": "1",
          "para_graph_num": "0",
          "size": "1"
        },
        "template_name": "模版"
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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:100001",
  "sub_msg": ""
}
```

## 备注
