# superm.product.queryProductSyncSubTask

> 查询根任务下的子任务列表

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.retail-store.superm.product.queryProductSyncSubTask` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/queryProductSyncSubTask` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2695 |
| 更新日期 | `2022-11-02` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `root_task_id` | body | number | 是 | 根任务ID | `7158439918014824735` |
| `page` | body | number | 是 | 起始页 (从0开始) | `0` |
| `size` | body | number | 是 | 每页尺寸 (最大值50) | `10` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com?app_key=your_appkey_here&method=&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `task_list` | array | 子任务列表 | `` |
| `page` | number | 起始页 (从0开始) | `0` |
| `size` | number | 每页尺寸 (最大值50) | `10` |
| `total` | number | 子任务总数 | `30` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / 2010001:查询Task信息出错，请稍后重试（sub_code: isv.business-failed:2010001） | 2010001:查询Task信息出错，请稍后重试 |
| `50002` | 业务处理失败 / 2010004:当前登录的用户信息不合法（sub_code: isv.business-failed:2010004） | 2010004:当前登录的用户信息不合法 |

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
  "code": 50002,
  "msg": "业务处理失败",
  "sub_code": "isv.business-failed:2010001",
  "sub_msg": "2010001:查询Task信息出错，请稍后重试"
}
```

## 备注
