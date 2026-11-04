# openCloud.createConfig

> 创建容器服务配置

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.cloud.openCloud.createConfig` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/openCloud/createConfig` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/158/7610 |
| 更新日期 | `2025-07-17` |

## 接口说明

- 文档书: 电商云API（版本 V1.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `elegant_config` | body | object | 是 | 优雅上下线 | `` |
| `  └ post_start` | body | string | 是 | 启动 | `"ad"` |
| `  └ pre_stop` | body | string | 是 | 停止 | `"fd"` |
| `  └ termination_grace_period_seconds` | body | string | 是 | 终止宽限 | `"fgsdf"` |
| `version` | body | string | 是 | 版本号 | `"1751923646621"` |
| `init_script` | body | string | 是 | 启动脚本 | `""` |
| `envs` | body | array | 是 | 环境变量参数配置 | `` |
| `  └ k` | body | string | 是 | 键 | `""` |
| `  └ v` | body | string | 是 | 值 | `""` |
| `  └ desc` | body | string | 是 | 描述 | `""` |
| `readiness` | body | object | 是 | 就绪检查 | `` |
| `  └ delay_time` | body | mixed | 是 | 检查延迟时间(s) | `0` |
| `  └ timeout` | body | mixed | 是 | 超时时间(s) | `0` |
| `  └ success_threshold` | body | mixed | 是 | 成功次数阀值 | `0` |
| `  └ port` | body | mixed | 否 | 端口号 | `0` |
| `  └ script_text` | body | string | 否 | script脚本文本 | `0` |
| `  └ is_check` | body | mixed | 否 | 是否开启检查 | `0` |
| `  └ detect_mode` | body | mixed | 否 | 健康检查探测方式:HTTP\|TCP\|SHELL_SCRIPT | `0` |
| `  └ duration_time` | body | mixed | 否 | 间隔时间(s) | `0` |
| `  └ failure_threshold` | body | mixed | 否 | 失败次数阀值 | `0` |
| `  └ url` | body | string | 否 | url | `""` |
| `file_mount` | body | array | 是 | 文件挂载 | `` |
| `  └ path` | body | string | 是 | 路径 | `"az"` |
| `  └ config` | body | string | 是 | 配置 | `"s"` |
| `  └ desc` | body | string | 是 | 描述 | `"s"` |
| `  └ mount_type` | body | mixed | 是 | 挂载类型 | `1` |
| `  └ volume` | body | object | 是 | 存储卷 | `` |
| `    └ source_name` | body | string | 是 | 源名称 | `""` |
| `    └ name` | body | string | 是 | 名称 | `"as"` |
| `    └ kind` | body | string | 是 | 存储卷固定传入 pvc | `"df"` |
| `schedule_rule` | body | object | 是 | 调度策略 | `` |
| `  └ node_taint_toleration` | body | array | 是 | 节点亲和性 | `` |
| `    └ key` | body | string | 是 | 键 | `"k"` |
| `    └ value` | body | string | 是 | 值 | `"v"` |
| `    └ is_system` | body | boolean | 是 | 是否为系统默认标签 | `true` |
| `  └ schedule_rule_effect_enum` | body | mixed | 是 | 调度效果 | `2` |
| `  └ pod_anti_affinity_with_hostname` | body | boolean | 是 | 是否开启容器优先调度到不同节点的能力(根据配置hostname反亲和性实现)，默认开启 true | `false` |
| `  └ node_labels` | body | array | 是 | 节点标签 | `` |
| `    └ value` | body | string | 是 | 键 | `"v"` |
| `    └ is_system` | body | boolean | 是 | 是否为系统默认标签 | `true` |
| `    └ key` | body | string | 是 | 值 | `"k"` |
| `volc_account_id` | body | mixed | 是 | 火山账号 | `2300003853` |
| `name` | body | string | 是 | 发布配置名称 | `7497139137958921770` |
| `cs_id` | body | string | 是 | 容器服务Id | `7524231212381340454` |
| `liveness` | body | object | 是 | 健康检查，也就是存活检查 | `` |
| `  └ is_check` | body | mixed | 是 | 是否开启检查 | `0` |
| `  └ detect_mode` | body | mixed | 是 | 健康检查探测方式:HTTP\|TCP\|SHELL_SCRIPT | `0` |
| `  └ duration_time` | body | mixed | 是 | 间隔时间(s) | `0` |
| `  └ url` | body | string | 是 | url | `""` |
| `  └ script_text` | body | string | 是 | script脚本文本 | `0` |
| `  └ delay_time` | body | mixed | 是 | 检查延迟时间(s) | `0` |
| `  └ timeout` | body | mixed | 是 | 超时时间(s) | `0` |
| `  └ failure_threshold` | body | mixed | 是 | 失败次数阀值 | `0` |
| `  └ success_threshold` | body | mixed | 是 | 成功次数阀值 | `0` |
| `  └ port` | body | mixed | 是 | 端口号 | `0` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/openCloud/createConfig?app_key=your_appkey_here&method=openCloud.createConfig&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | 成功 | 正常处理 |

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
  "sub_code": "",
  "sub_msg": ""
}
```

## 备注
