# logistics.fetchBluetoothCmd

> 电子面单场景下，获取蓝牙的打印指令

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.waybill.logistics.fetchBluetoothCmd` |
| 中文名 | 电子面单场景下，获取蓝牙的打印指令 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/logistics/fetchBluetoothCmd` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1262/4142 |
| 更新日期 | `2023-06-28` |

## 接口说明

- 文档书: 电子面单API（版本 V1.05）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `waybill_applies` | body | array | 是 | 运单信息，一次最多请求200单。 | `` |
| `  └ track_no` | body | string | 是 | 运单号 | `12345` |
| `  └ std_template_code` | body | string | 是 | 标准模板code。已支持的模板信息 https://bytedance.feishu.cn/sheets/VFmQsxJNth8t2OtWWDJca5BbnDb?sheet=p92gXy | `zt_76_130_v2` |
| `  └ cus_template_url` | body | string | 否 | 自定义区模板url。（传了cus_print_data后url和code其中一个必传） | `https://lf3-cm.ecombdstatic.com/obj/logistics-davinci/publicElements/zt_76_130_v2_1633693132.xml` |
| `  └ cus_template_code` | body | string | 否 | 自定义区模板code（支持模板设计器的模板）。设计器地址：https://cloudprint.douyinec.com/ | `1234` |
| `  └ cus_print_data` | body | string | 否 | 自定义区json数据 | `{"customKey":"customValue"}` |
| `remote_print_config` | body | object | 否 | 打印配置 | `` |
| `  └ need_top_logo` | body | boolean | 否 | 是否需要打印物流商logo | `true` |
| `  └ horizontal_offset` | body | string | 否 | 水平偏移量，单位mm | `1` |
| `  └ vertical_offset` | body | string | 否 | 垂直偏移量，单位mm | `1` |
| `  └ print_direction` | body | string | 否 | [必传字段] 打印方向。normal-正常；reverse-反转。 | `normal` |
| `  └ printer_name` | body | string | 是 | 打印机名称。查看已支持的打印机信息 https://bytedance.feishu.cn/sheets/VFmQsxJNth8t2OtWWDJca5BbnDb?sheet=44acf5 | `QR-488BT_xx` |
| `cmd_type` | body | string | 是 | 打印机指令类型。CPCL；TSPL | `CPCL` |
| `cmd_encode` | body | string | 是 | 编码方式。 origin：原串->字节数组->base64； gbk：原串->字节数组->gbk->base64； gzip_byte：原串->字节数组->gzip压缩->base64； | `gzip_byte` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/yunc/erpInboundCancel?app_key=your_appkey_here&method=yunc.erpInboundCancel&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `waybill_infos` | array | 运单的打印指令 | `` |
| `err_infos` | array | 错误信息 | `` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数有误，请检查请求参数（sub_code: isv.parameter-invalid:100001） | 检查入参 |
| `50002` | 业务处理失败 / 系统错误，请稍后重试（sub_code: isv.business-failed:100002） | 联系开发人员 |
| `50002` | 业务处理失败 / 101115:该模板不存在（sub_code: isv.business-failed:101115） | 检查模板信息 |
| `50002` | 业务处理失败 / 101113:暂不支持该品牌的打印机型号（sub_code: isv.business-failed:101113） | 检查打印机名称 |

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
  "sub_code": "isv.parameter-invalid:100001",
  "sub_msg": "参数有误，请检查请求参数"
}
```

## 备注
