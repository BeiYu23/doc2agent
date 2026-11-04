# supplyChain.supplyProductV2.getComponentTemplate

> 分页查询模板列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.supply-chain.supplyChain.supplyProductV2.getComponentTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/172/6675 |
| 更新日期 | `2024-07-04` |

## 接口说明

- 文档书: 供销平台API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page_num` | body | mixed | 否 | 页号，从0开始 | `0` |
| `page_size` | body | mixed | 否 | 每页大小 | `100` |
| `template_type` | body | string | 否 | 模板类型: size_info(尺码表) | `size_info` |
| `template_sub_type` | body | string | 否 | 组件模板子类型；clothing -服饰；undies-内衣；shoes 鞋靴；children_clothing-童装 | `clothing` |
| `template_id` | body | mixed | 否 | 指定template_id查询，主要用于编辑组件时预览 | `111` |
| `shareable` | body | boolean | 否 | 是否共享 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyChain.supplyProductV2.getComponentTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `code` | mixed | code | `0` |
| `msg` | string | msg | `“”` |
| `component_template_info_list` | array | 返回的组件模板信息 | `` |
| `total_num` | mixed | 总量 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

## 响应示例

成功：

```json
{
  "data": {
    "code": "0",
    "component_template_info_list": [
      {
        "category_id": "0",
        "component_data": "xxx",
        "component_front_data": "",
        "create_time": "0",
        "image": {
          "height": "0",
          "source": "",
          "url": "",
          "width": "0"
        },
        "shareable": "0",
        "template_id": "0",
        "template_name": "xxx",
        "template_sub_type": "",
        "template_type": "",
        "update_time": "0"
      }
    ],
    "msg": "“”",
    "total_num": "0"
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
