# material.createFolder

> 创建文件夹

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.createFolder` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/createFolder` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/946 |
| 更新日期 | `2024-06-12` |

## 接口说明

- 文档书: 素材中心API（版本 V4.03）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `name` | body | string | 是 | 文件夹名称。最多20字符 | `商品图片素材` |
| `parent_folder_id` | body | string | 否 | 父文件夹id，根目录为0。不传该参数默认在根目录下创建文件夹 | `70036799713989921721250` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `folder_id` | string | 文件夹id，全局唯一 | `7000254886243811628` |
| `parent_folder_id` | string | 父文件夹id，全局唯一 | `7000254886243746092` |
| `name` | string | 文件夹名称 | `商品图片素材` |
| `type` | mixed | 文件夹类型。0-用户自建 1-默认 2-系统文件夹 | `1` |
| `is_new` | boolean | 判断文件夹是否为新创建的； 若父文件夹下存在同名文件夹，创建时返回该同名文件夹id，is_new为false； 若不存在同名文件夹且创建成功，则is_new为true，表示为新创建的文件夹。 | `true` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误，请调整参数（sub_code: isv.parameter-invalid:20001） | 参数不正确，调整参数 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10004） | 系统异常，请稍后重试 |
| `40004` | 非法的参数 / 同一父文件夹下，最多有100个子文件夹（sub_code: isv.parameter-invalid:21001） | 同一父文件夹下，最多有100个子文件夹 |
| `40004` | 非法的参数 / 待创建的文件夹属性和父级文件夹属性不一致（sub_code: isv.parameter-invalid:21007） | 图片文件夹只能存文件，视频文件夹只能存视频 |
| `20000` | 系统错误 / 系统异常，请稍后重试（sub_code: isp.service-error:10003） | 系统异常，请稍后重试 |
| `50002` | 业务处理失败 / 文件夹层数超出最大限制（sub_code: isv.business-failed:21002） | 文件夹层数超出最大限制 |
| `50002` | 业务处理失败 / 素材中心尚未初始化，请联系客服或稍后重试（sub_code: isv.business-failed:30003） | 素材中心尚未初始化，请联系客服或稍后重试 |
| `50002` | 业务处理失败 / 30004:仅支持正常运营的商家创建素材/文件夹（sub_code: isv.business-failed:30004） | 30004:仅支持正常运营的商家创建素材/文件夹 |

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
  "sub_code": "isv.parameter-invalid:20001",
  "sub_msg": "参数错误，请调整参数"
}
```

## 备注
