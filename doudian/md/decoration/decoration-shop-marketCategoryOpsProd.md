# shop.marketCategoryOpsProd

> 基于商品维度更新分类页绑定关系

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.marketCategoryOpsProd` |
| 中文名 | 基于商品维度更新分类页绑定关系 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/marketCategoryOpsProd` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/6242 |
| 更新日期 | `2024-05-06` |

## 接口说明

- 文档书: 店铺装修API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `infos` | body | array | 是 | 需要更新的item、分类关系 | `` |
| `  └ item_id` | body | string | 是 | 商品ID | `7337543193975587098` |
| `  └ item_type` | body | mixed | 是 | 类型枚举，表示item_id归属类型 1：商品 | `1` |
| `  └ category_id_list` | body | array | 是 | 店铺分类页生效的叶子类目ID，支持一二级分类。 如果一级分类下面存在子分类，则绑定失败。 | `["7337543193975587098","7337543193975587091","7337543193975587092"]` |
| `  └ ops_type` | body | mixed | 是 | 操作类型 1：添加 2：删除 3：移动(先删除原分类，再添加到新分类) | `1` |
| `tmp_id` | body | mixed | 是 | 页面ID，建议指定对应要更新的页面ID | `7337543193975587098` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `item_tips` | string | 商品提示信息 | `{"7337543193975587098":"商品信息不存在"}` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 更新类目校验失败（sub_code: isv.parameter-invalid:23002） | 检查参数 |
| `50002` | 业务处理失败 / 更新类目失败（sub_code: isv.business-failed:23003） | 稍后重试，或减少处理量 |
| `50002` | 业务处理失败 / 20110:当前页面已删除（sub_code: isv.business-failed:20110） | 20110:当前页面已删除 |
| `50002` | 业务处理失败 / 40016:网络异常，请稍后重试（sub_code: isv.business-failed:40016） | 40016:网络异常，请稍后重试 |

## 响应示例

成功：

```json
{
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
  "sub_code": "isv.parameter-invalid:23002",
  "sub_msg": "更新类目校验失败"
}
```

## 备注
