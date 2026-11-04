# material.easyShuttle

> 一键删除

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.material.material.easyShuttle` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/material/easyShuttle` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/69/1955 |
| 更新日期 | `2022-09-06` |

## 接口说明

- 文档书: 素材中心API（版本 V1.04）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `folder_id_list` | body | array | 是 | 文件夹ID列表，对该文件夹下的文件夹或素材进行操作；0:开放平台；1:图片根目录；2:视频根目录；-1:回收站 | `["0"]` |
| `operate_type` | body | string | 是 | 操作类型：移到回收站：to_recycle，彻底删除：delete_forever | `to_recycle` |
| `material_type_list` | body | array | 是 | 操作的素材类型 | `["photo","video"]` |
| `only_material` | body | boolean | 否 | 是否只操作素材 | `true` |
| `create_time_end` | body | string | 否 | 所操作的素材或文件夹的创建时间在该时间点之前 | `2022-02-22 22:22:22` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/material/easyShuttle?app_key=your_appkey_here&method=material.easyShuttle&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数错误（sub_code: isv.parameter-invalid:20001） | 修改参数 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:10007） | 重试 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:10004） | 重试 |
| `20000` | 系统错误 / 系统内部错误（sub_code: isp.service-error:10003） | 重试 |
| `50002` | 业务处理失败 / 22004:数据可能已被修改，请刷新后重新提交（sub_code: isv.business-failed:22004） | 22004:数据可能已被修改，请刷新后重新提交 |

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
  "sub_msg": "参数错误"
}
```

## 备注
