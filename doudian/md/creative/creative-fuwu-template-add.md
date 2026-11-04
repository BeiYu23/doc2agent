# fuwu.template.add

> 创建或编辑内容模版服务

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.creative.fuwu.template.add` |
| 中文名 | 创建或编辑内容模版服务 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/fuwu/template/add` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1358/4198 |
| 更新日期 | `2024-01-03` |

## 接口说明

- 文档书: 创意管理API（版本 SNAPSHOT）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `template_code` | body | string | 是 | 外部模版code | `ccccc` |
| `template_name` | body | string | 是 | 模版名称 | `新品上架模版` |
| `template_info` | body | object | 是 | 模版基础信息 | `` |
| `  └ size` | body | mixed | 是 | 枚举值1、1:1 ,2、 3:4 | `1` |
| `  └ para_graph_num` | body | mixed | 否 | 段落数量，默认为0，不展示段落数量 | `1` |
| `  └ displaying_text` | body | mixed | 是 | 是否含字幕/文案 0 不含 1 含 | `0` |
| `service_type` | body | mixed | 是 | 服务类型：1主图视频2图文 | `1` |
| `skus` | body | array | 是 | 版本信息 | `` |
| `  └ price_type` | body | mixed | 是 | 价格类型 0、付费版 1、免费版 2、试用版 3、加量包 ，其中存在免费版不可有试用/付费;存在试用版，必须至少传入一个付费版;付费版/加量包需传入价格 | `1` |
| `  └ price` | body | mixed | 否 | 模版服务价格，付费版/加量包必传入，单位为分 | `0` |
| `  └ duration_id` | body | mixed | 是 | 默认参数0无需设置周期, 时间周期枚举数据，6:30天、3:6个月、4:1年、10:7天、11:15天 | `6` |
| `  └ usage_count` | body | mixed | 是 | 服务可使用次数 | `100` |
| `suite_industry` | body | object | 是 | 适用行业信息数据 | `` |
| `  └ suite_type` | body | mixed | 是 | 适用类型 1: 通用 2:指定电商行业一级类目id | `2` |
| `  └ industry_ids` | body | array | 否 | 电商一级类目信息列表2:玩具乐器,3:二手商品,4:服饰内衣,5:个护家清,6:礼品文创,7:智能家居,8:生鲜,9:美妆,10:母婴宠物,11:鲜花园艺,12:本地生活,13:食品饮料,14:3C数码家电,15:图书教育,16:鞋靴箱包,17:虚拟充值,18:运动户外,19:钟表配饰,20:珠宝文玩,21:奢侈品,22:医疗健康,23:酒类,24:滋补保健,5012:汽车整车 | `[123]` |
| `preview_info` | body | object | 是 | 预览信息数据 | `` |
| `  └ video_path` | body | string | 否 | 主图视频时必传 | `xxx.mp4` |
| `  └ thumbnail` | body | string | 否 | 主图视频必传 | `cover.jpg` |
| `  └ picture_paths` | body | array | 否 | 图文模版时必传 | `['1.jpeg']` |
| `labels` | body | array | 是 | 模版类型 1、产品讲解 2、种草 | `[1,2]` |
| `service_id` | body | mixed | 否 | 编辑时传入服务id | `12345` |
| `is_hidden` | body | mixed | 是 | 是否在服务市场隐藏 | `0` |
| `service_course` | body | string | 否 | 服务教程 | `服务教程内容` |
| `custom_content` | body | string | 否 | 自定义模块 | `自定义模块内容` |
| `support_terminal` | body | array | 否 | 支持的端类型(1:PC 2:APP） | `[1,2]` |
| `is_by_times_fulfill` | body | boolean | 否 | 按次进行履约(按次结算&退款), 支持限用次数与加量包 | `true` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/fuwu/template/add?app_key=your_appkey_here&method=fuwu.template.add&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `service_id` | mixed | 服务id(对应一个模板) | `123` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 100001:参数错误，素材未审核，不允许创建（sub_code: isv.parameter-invalid:100001） | 检查相关参数 |
| `50002` | 业务处理失败 / 300270:已存在同名的服务，请更换服务名称（sub_code: isv.business-failed:300270） | 检查服务名称或模版code参数 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:300200） | 按 sub_code 定位问题后处理 |
| `50002` | 业务处理失败（sub_code: isv.business-failed:200070） | 按 sub_code 定位问题后处理 |

## 响应示例

成功：

```json
{
  "data": {
    "service_id": "123"
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
  "sub_code": "isv.parameter-invalid:100001",
  "sub_msg": "100001:参数错误，素材未审核，不允许创建"
}
```

## 备注
