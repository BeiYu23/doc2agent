# 医生接诊

> medicine.doctorAcceptConsult — 医生接诊

| 元信息 | 值 |
| --- | --- |
| 中文名 | 医生接诊 |
| 文档地址 | `/docs/doudian/hospital/hospital-medicine-doctorAcceptConsult` |
| 接口 ID | `doudian.hospital.medicine.doctorAcceptConsult` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/medicine/doctorAcceptConsult` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1451/5899 |
| 更新日期 | `2024-05-06` |

## 接口说明

- 文档书: 互联网医院（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `consult_id` | body | mixed | 是 | 问诊单id | `6917546006426224265` |
| `doctor_name` | body | string | 是 | 医生名称 | `测试医生` |
| `img` | body | string | 是 | 医生头像 | `https://p6-open-static.ecombdimg.com/tos-cn-i-o8j9kkde8i/86976da6c8034393a9074b21d465b2d6~tplv-o8j9kkde8i-1.image` |
| `hospital_name` | body | string | 是 | 互联网医院名称（需要和服务市场注册的名称保持一致） | `测试医院` |
| `doc_practice_cert` | body | string | 是 | 医生执业证编号 | `1231231233` |
| `dept` | body | string | 是 | 科室 | `妇科` |
| `level` | body | string | 是 | 医生级别 | `主治医生` |
| `profile` | body | string | 是 | 医生简介 | `我是xx医院xx科室医生` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/medicine/doctorAcceptConsult?app_key=your_appkey_here&method=medicine.doctorAcceptConsult&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `50002` | 业务处理失败 / -1:系统错误，请稍后重试（sub_code: isv.business-failed:-1） | 排查 |
| `50002` | 业务处理失败 / 100001:问诊当前状态[Cancel]不支持更新.（sub_code: isv.business-failed:500014） | 排查 |
| `50002` | 业务处理失败 / 500011:问诊信息不存在（sub_code: isv.business-failed:500011） | 排查 |

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
  "sub_code": "isv.business-failed:-1",
  "sub_msg": "-1:系统错误，请稍后重试"
}
```

## 备注
