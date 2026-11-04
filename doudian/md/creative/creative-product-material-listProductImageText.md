# product.material.listProductImageText

> 商品元图文创意查询

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.creative.product.material.listProductImageText` |
| 中文名 | 商品元图文创意查询 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4244 |
| 更新日期 | `2023-08-02` |

## 接口说明

- 文档书: 创意管理API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `page` | body | number | 是 | 当前页数，从0开始 | `1` |
| `size` | body | number | 是 | 一页数量 | `10` |
| `status` | body | array | 否 | 作品(素材)状态 | `-1:已删除 0:待发布 1:审核中 2:已上线 3:审核未通过` |
| `material_ids` | body | array | 否 | 作品(素材)id | `[1111,2222]` |
| `process_status` | body | number | 否 | (作品)素材业务状态 | `0:未发布  1: 发布中  2:发布成功  3:发布失败` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `total` | number | 查询总数 | `11` |
| `data` | array | 数据 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效入参（sub_code: isv.parameter-invalid:2012004） | isv检查入参 |
| `20000` | 系统错误（sub_code: isp.service-error:2012001） | 重试 |
| `50002` | 业务处理失败 / 查询失败（sub_code: isv.business-failed:2012013） | 重试或者联系 |
| `50002` | 业务处理失败 / 20121045:Post "http://search.apigateway.proxy$ecom_product_material/product_center_product_card/_search?routing=40782657": create connection to [10.147.18.45:9996] failed : dial tcp 10.147.18.45:9996: connect: network is unreachable（sub_code: isv.business-failed:20121045） | 20121045:Post "http://search.apigateway.proxy$ecom_product_material/product_center_product_card/_search?routing=40782657": create connection to [10.147.18.45:9996] failed : dial tcp 10.147.18.45:9996: connect: network is unreachable |

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
  "sub_code": "isv.parameter-invalid:2012004",
  "sub_msg": "无效入参"
}
```

## 备注
