# 商品元图文创意创建

> product.material.createProductImageText — 商品元图文创意创建

| 元信息 | 值 |
| --- | --- |
| 中文名 | 商品元图文创意创建 |
| 文档地址 | `/docs/doudian/creative/creative-product-material-createProductImageText` |
| 接口 ID | `doudian.creative.product.material.createProductImageText` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4237 |
| 更新日期 | `2023-12-28` |

## 接口说明

- 文档书: 创意管理API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | 素材名称 | `创意` |
| `pic_urls` | body | array | 是 | 元数据图片列表 | `["https://p3-aio.ecombdimg.com/obj/ecom-shop-material/bMLccs_m_de71e7048436b02bc41cc6fc2beeca07_sx_80208_www1000-1000\","https://p3-aio.ecombdimg.com/obj/ecom-shop-material/bMLccs_m_de71e7048436b02bc41cc6fc2beeca07_sx_80208_www1000-1000\"]` |
| `subtitle` | body | string | 是 | 图文讲解 | `这个夏天不想被大家说是“小肉球”了吧,那你一定要试试我们这款女装套装,这件连衣裙版型非常正,而且还有加宽的设计,可以藏起来多余的赘肉,从视觉上就很显瘦,面料也很重要,这件选用高档雪纺面料,清新、透气、质地冰凉、光泽度强,更显得年轻和活力,整体的设计给人一种古风古风时尚的感觉,真心建议每一位女士都去尝试一下` |
| `bgm_id` | body | string | 是 | 背景音乐id | `12323123` |
| `product_id` | body | mixed | 否 | 绑定商品id | `1111` |
| `is_direct_apply` | body | boolean | 否 | 创建完是否直接发布应用，true-是，fasle-否，默认fasle； | `true` |
| `image_text_template_id` | body | string | 否 | 图文生成所用模板 | `31312312312313` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=product.material.createProductImageText&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | mixed | (作品)素材id | `1111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效入参（sub_code: isv.parameter-invalid:2012004） | isv检查入参 |
| `20000` | 系统错误（sub_code: isp.service-error:2012001） | 重试 |
| `50002` | 业务处理失败 / 文本黑词校验失败（sub_code: isv.business-failed:2012013） | 修改后重试 |

## 响应示例

成功：

```json
{
  "data": {
    "material_id": "1111"
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
  "sub_code": "isv.parameter-invalid:2012004",
  "sub_msg": "无效入参"
}
```

## 备注
