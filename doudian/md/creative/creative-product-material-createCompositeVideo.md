# product.material.createCompositeVideo

> 素材元视频创意创建

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.creative.product.material.createCompositeVideo` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `YOUR_SECRET_KEY` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4242 |
| 更新日期 | `2023-08-01` |

## 接口说明

- 文档书: 创意管理API（版本 V1.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 否 | (作品)素材名称 | `创意素材` |
| `vid` | body | string | 是 | 资源文件uri,视频vid | `v0377bg10003civ1de3c77u6bfuh84ag` |
| `product_id` | body | number | 否 | 商品id | `111111111` |
| `pass_through_extra` | body | string | 否 | 扩展属性，开发者自定义数据，存放主图视频的编辑信息，平台不做逻辑处理 | `{}` |
| `is_direct_apply` | body | boolean | 否 | 创建完是否直接发布应用，true-是，fasle-否，默认fasle； | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/cloudCreateInboundOrder?app_key=your_appkey_here&method=yunc.cloudCreateInboundOrder&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `material_id` | number | (作品)素材id | `1111111` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 无效参数（sub_code: isv.parameter-invalid:2012004） | isv检查入参 |
| `20000` | 系统错误（sub_code: isp.service-error:2012001） | 重试 |
| `50002` | 业务处理失败 / 20121060:系统异常\|视频长宽比错误，请上传1:1比例或者3:4比例或者9:16比例的主图视频（sub_code: isv.business-failed:20121060） | 20121060:系统异常\|视频长宽比错误，请上传1:1比例或者3:4比例或者9:16比例的主图视频 |
| `50002` | 业务处理失败 / 20121025:当前商品非上架状态（sub_code: isv.business-failed:20121025） | 20121025:当前商品非上架状态 |

## 响应示例

成功：

```json
{
  "data": {
    "data": ""
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
  "sub_msg": "无效参数"
}
```

## 备注
