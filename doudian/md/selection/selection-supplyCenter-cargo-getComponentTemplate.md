# supplyCenter.cargo.getComponentTemplate

> 分页查询尺寸模板

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.selection.supplyCenter.cargo.getComponentTemplate` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1438/5332 |
| 更新日期 | `2023-10-25` |

## 接口说明

- 文档书: 精选货源API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_type` | body | string | 否 | 模板类型: size_info(尺码表) | `size_info` |
| `template_sub_type` | body | string | 否 | 组件模板子类型；clothing -饰；undies-内衣；shoes 鞋靴；children_clothing-童装 | `clothing` |
| `template_id` | body | number | 否 | 模板ID | `101` |
| `shareable` | body | boolean | 否 | 是否设置为公有模板(多个商品可共用)。true-是，false-不是；不传默认true | `true` |
| `page_num` | body | number | 否 | 页码，从0开始，最大支持100 | `0` |
| `page_size` | body | number | 否 | 每页条数，最大支持20；page_size和template_id二选一入参 | `20` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=supplyCenter.cargo.getComponentTemplate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `component_template_info_list` | array | 尺码模板列表 | `` |
| `total_num` | number | 总数 | `200` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参照查询模板列表接口（sub_code: isv.parameter-invalid:66666） | https://op.jinritemai.com/docs/api-docs/14/1990 |

## 响应示例

成功：

```json
{
  "data": {
    "component_template_info_list": [
      {
        "category_id": "22465",
        "component_data": "{\"title\":\"衣服尺码title\",\"sub_title\":\"衣服尺码desc\",\"selected_size\":[\"XS\",\"M\"],\"selected_specs\":[\"身高（cm）\",\"体重（斤）\",\"胸围（cm）\"],\"config\":{\"M\":{\"体重（斤）\":\"70\",\"胸围（cm）\":\"67\",\"身高（cm）\":\"110\"},\"XS\":{\"体重（斤）\":\"55\",\"胸围（cm）\":\"66\",\"身高（cm）\":\"100\"}}}",
        "component_front_data": "{\"title\":\"衣服尺码title\",\"desc\":\"衣服尺码desc\",\"tempName\":\"0711衣服模板tempName\",\"configTable\":[{\"size\":\"XS\",\"specMap\":{\"身高（cm）\":\"100\",\"体重（斤）\":\"55\",\"胸围（cm）\":\"66\"}},{\"size\":\"M\",\"specMap\":{\"身高（cm）\":\"110\",\"体重（斤）\":\"70\",\"胸围（cm）\":\"67\"}}],\"selectedSpecs\":[\"身高（cm）\",\"体重（斤）\",\"胸围（cm）\"],\"specOptions\":[\"身高1（cm）\",\"体重1（斤）\",\"胸围1（cm）\"],\"selectedSize\":[\"XS\",\"M\"]}",
        "create_time": "1",
        "image": {
          "height": "256",
          "url": "http://xx.xxx",
          "width": "200"
        },
        "shareable": "false",
        "template_id": "101",
        "template_name": "模板名称1",
        "template_sub_type": "clothing",
        "template_type": "size_info",
        "update_time": "1"
      }
    ],
    "total_num": "200"
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
  "code": 40004,
  "msg": "非法的参数",
  "sub_code": "isv.parameter-invalid:66666",
  "sub_msg": "参照查询模板列表接口"
}
```

## 备注
