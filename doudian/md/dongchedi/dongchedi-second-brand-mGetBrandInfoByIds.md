# second.brand.mGetBrandInfoByIds

> 【二方接口】根据brand_id查询品牌信息,翻页单次数量不超过300

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.dongchedi.second.brand.mGetBrandInfoByIds` |
| 中文名 | 【二方接口】根据brand_id查询品牌信息 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/second/brand/mGetBrandInfoByIds` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1544/7016 |
| 更新日期 | `2024-10-21` |

## 接口说明

- 文档书: 懂车帝业务（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `uid` | body | string | 否 | 商业化账号组uid，用作鉴权 | `15495388485` |
| `shopId` | body | mixed | 否 | 店铺ID | `5055915` |
| `auditStatus` | body | array | 否 | AuditStatus | `[]` |
| `enableDeDuplicate` | body | boolean | 否 | 启用去重 如果存con'f'ig在重复ID则返回去重后的品牌信息 | `false` |
| `bizTypes` | body | array | 否 | BizTypes | `[]` |
| `brandIds` | body | array | 否 | BrandIds | `[]` |
| `status` | body | mixed | 否 | Status | `4288570` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=second.brand.mGetBrandInfoByIds&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `brands` | array | Brands | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `20000` | 系统错误 / uid不能为空（sub_code: isp.service-error:300001） | uid不能为空 |
| `20000` | 系统错误 / shopId不能为空（sub_code: isp.service-error:300002） | shopId不能为空 |
| `20000` | 系统错误 / 店铺鉴权失败（sub_code: isp.service-error:500004） | 店铺鉴权失败 |

## 响应示例

成功：

```json
{
  "data": {
    "brands": [
      {
        "key": "key",
        "value": {
          "brandId": "1875927",
          "brandNameCN": "f74467a8",
          "brandNameEN": "d0483ece"
        }
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
  "sub_msg": "uid不能为空"
}
```

## 备注
