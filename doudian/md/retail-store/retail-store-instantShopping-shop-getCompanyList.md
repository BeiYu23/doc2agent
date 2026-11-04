# instantShopping.shop.getCompanyList

> 查询管理单元列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.instantShopping.shop.getCompanyList` |
| 中文名 | 查询管理单元列表 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/7041 |
| 更新日期 | `2024-11-07` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_size` | body | mixed | 是 | 默认为10 最大100 | `10` |
| `company_id_list` | body | array | 否 | 管理单元id列表 | `[123, 124]` |
| `names` | body | array | 否 | 管理单元名称列表 [精确搜索] | `["测试管理单元-1", "测试管理单元-2"]` |
| `status_list` | body | array | 否 | 管理单元状态列表 0-初始化 1-审核中 2-审核通过 3-审核拒绝 4-完成入驻 | `[0, 1]` |
| `page` | body | mixed | 是 | 从1开始 | `1` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=instantShopping.shop.getCompanyList&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | mixed | 查询总数 | `10` |
| `data` | array | 管理单元列表 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "data": [
      {
        "company_id": "123",
        "name": "测试管理单元",
        "parent_id": "123",
        "parent_name": "测试总部组织",
        "status": "1"
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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
