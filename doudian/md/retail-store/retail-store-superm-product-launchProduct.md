# 上架商品

> superm.product.launchProduct — 上架商品

| 元信息 | 值 |
| --- | --- |
| 中文名 | 上架商品 |
| 文档地址 | `/docs/doudian/retail-store/retail-store-superm-product-launchProduct` |
| 接口 ID | `doudian.retail-store.superm.product.launchProduct` |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/superm/product/launchProduct` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/1033/2666 |
| 更新日期 | `2026-07-15` |

## 接口说明

- 文档书: 门店管理API【即时零售】（版本 V3.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `product_id` | body | string | 是 | 商品ID，支持主品上架，支持子品上架； (主品需要审核通过后上架) | `3576410646054571500` |
| `outer_product_id` | body | string | 否 | 推荐使用，外部商家编码，支持字符串。 | `232334` |
| `store_id` | body | string | 否 | 小时达二期店铺场景才可以传，小时达二期场景可以通过传入主品id+门店id对该门店下的子品进行操作 | `12345` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.YOUR_SECRET_KEY?app_key=your_appkey_here&method=superm.product.launchProduct&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| 无 | - | - | - |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100003） | 请参考能力文档传入合法参数 |
| `40004` | 非法的参数 / 参数非法（sub_code: isv.parameter-invalid:4100002） | 请参考能力文档传入合法参数 |
| `40002` | 缺少必选参数 / 缺少必填参数（sub_code: isv.missing-parameter:4100001） | 请参考能力文档传入合法参数 |
| `50002` | 业务处理失败 / 业务系统异常，请联系开平人员（sub_code: isv.business-failed:5000001） | 业务处理失败 |
| `20000` | 系统错误 / 系统异常，可尝试重试（sub_code: isp.service-error:5000002） | 系统异常，可尝试重试 |
| `50002` | 业务处理失败 / 110502037:主品非售卖中状态，请先上架主品（sub_code: isv.business-failed:110502037） | 110502037:主品非售卖中状态，请先上架主品 |
| `50002` | 业务处理失败 / 110330102:请修改“售后服务”，该类目已不再支持该售后政策（sub_code: isv.business-failed:110330102） | 110330102:请修改“售后服务”，该类目已不再支持该售后政策 |
| `50002` | 业务处理失败 / 110200024:发布当前类目商品，还需缴纳5.67元保证金，点击“<a href='/ffa/content/shop_deposit' target="_blank">立即充值</a>”补全对应保证金后方可发布商品，详见<a href='https://school.jinritemai.com/doudian/web/article/101830?from=shop_table&btm_ppre=a4977.b4369.c0.d0&btm_pre=a4977.b6444.c0.d0&btm_show_id=2406dd1e-2c4d-47d1-bd34-4e347a3c230a' target="_blank">《抖音电商类目保证金规则》</a><br /><br />更多充值操作请前往<a href='https://fxg.jinritemai.com/ffa/content/shop_deposit' target="_blank">保证金首页</a>（sub_code: isv.business-failed:110200024） | 110200024:发布当前类目商品，还需缴纳5.67元保证金，点击“<a href='/ffa/content/shop_deposit' target="_blank">立即充值</a>”补全对应保证金后方可发布商品，详见<a href='https://school.jinritemai.com/doudian/web/article/101830?from=shop_table&btm_ppre=a4977.b4369.c0.d0&btm_pre=a4977.b6444.c0.d0&btm_show_id=2406dd1e-2c4d-47d1-bd34-4e347a3c230a' target="_blank">《抖音电商类目保证金规则》</a><br /><br />更多充值操作请前往<a href='https://fxg.jinritemai.com/ffa/content/shop_deposit' target="_blank">保证金首页</a> |
| `50002` | 业务处理失败 / 2010053:所选类目资质已失效，可以选择保存草稿，待资质审核完成后再提交（sub_code: isv.business-failed:2010053） | 2010053:所选类目资质已失效，可以选择保存草稿，待资质审核完成后再提交 |
| `50002` | 业务处理失败 / 2010042:商品已删除，请先将商品恢复，再做修改（sub_code: isv.business-failed:2010042） | 2010042:商品已删除，请先将商品恢复，再做修改 |
| `50002` | 业务处理失败 / 110250169:该类目要求上传尺码组件信息，请补充后提交（sub_code: isv.business-failed:110250169） | 110250169:该类目要求上传尺码组件信息，请补充后提交 |
| `50002` | 业务处理失败 / 110215105:属性值不存在， propertyId:4118、propertyName:贮存条件（sub_code: isv.business-failed:110215105） | 110215105:属性值不存在， propertyId:4118、propertyName:贮存条件 |
| `50002` | 业务处理失败 / 110215118:属性包装方式的属性值不在属性值选项列表中，属性值的自定义类型diy_type需要=1（sub_code: isv.business-failed:110215118） | 110215118:属性包装方式的属性值不在属性值选项列表中，属性值的自定义类型diy_type需要=1 |
| `50002` | 业务处理失败 / 110215137:属性“包冰率“的填写格式已升级，属性值“0“不符合填写格式要求，请点击属性输入框重新填写（sub_code: isv.business-failed:110215137） | 110215137:属性“包冰率“的填写格式已升级，属性值“0“不符合填写格式要求，请点击属性输入框重新填写 |
| `50002` | 业务处理失败 / 110101150:商品标题最短不能低于4个汉字（8个字符）（sub_code: isv.business-failed:110101150） | 110101150:商品标题最短不能低于4个汉字（8个字符） |
| `50002` | 业务处理失败 / 110250016:主图：第 1 张不符合格式要求，请上传 JPG/JPEG/PNG 格式，<a href='https://bytedance.larkoffice.com/wiki/Dn0twtf5kiBGr3km7gWc1XjInvg' target='_blank'>文件格式要求/转换方式请参考</a>（sub_code: isv.business-failed:110250016） | 110250016:主图：第 1 张不符合格式要求，请上传 JPG/JPEG/PNG 格式，<a href='https://bytedance.larkoffice.com/wiki/Dn0twtf5kiBGr3km7gWc1XjInvg' target='_blank'>文件格式要求/转换方式请参考</a> |
| `50002` | 业务处理失败 / 110310110:当前商品正在参与活动 华南2613档促销上翻，商品SKU价格不得低于活动到手价格￥40.90元，请修改后重新提交。（sub_code: isv.business-failed:110310110） | 110310110:当前商品正在参与活动 华南2613档促销上翻，商品SKU价格不得低于活动到手价格￥40.90元，请修改后重新提交。 |
| `50002` | 业务处理失败 / 110405002:系统异常（sub_code: isv.business-failed:110405002） | 110405002:系统异常 |
| `50002` | 业务处理失败 / 110290001:请上传动物检验检疫证明（sub_code: isv.business-failed:110290001） | 110290001:请上传动物检验检疫证明 |
| `50002` | 业务处理失败 / 110220143:“类目属性”中的【保质期】填写格式已调整,请根据下方属性项的最新格式重新填写（sub_code: isv.business-failed:110220143） | 110220143:“类目属性”中的【保质期】填写格式已调整,请根据下方属性项的最新格式重新填写 |
| `50002` | 业务处理失败 / 110360108:品牌资质规则查询失败（sub_code: isv.business-failed:110360108） | 110360108:品牌资质规则查询失败 |
| `50002` | 业务处理失败 / 2010318:当前商品选择的品牌信息已过期，请更新品牌资质信息，或更换商品品牌后，再提交商品发布。（sub_code: isv.business-failed:2010318） | 2010318:当前商品选择的品牌信息已过期，请更新品牌资质信息，或更换商品品牌后，再提交商品发布。 |
| `50002` | 业务处理失败 / 110220151:“类目属性”中的【保质期】填写不符合要求,2天中2数值须不低于:3.6, 请至抖店商品编辑页面刷新页面重试（sub_code: isv.business-failed:110220151） | 110220151:“类目属性”中的【保质期】填写不符合要求,2天中2数值须不低于:3.6, 请至抖店商品编辑页面刷新页面重试 |
| `50002` | 业务处理失败 / 2010020:绿色食品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号 有机食品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号 无公害农产品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号（sub_code: isv.business-failed:2010020） | 2010020:绿色食品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号有机食品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号无公害农产品认证编号：填写内容不得包含非法字符/空格，请重新输入正确编号 |
| `50002` | 业务处理失败 / 110502062:移动电源缺少产品数字标识，无法上架。请编辑商品，在"产品数字标识"专区填写（sub_code: isv.business-failed:110502062） | 110502062:移动电源缺少产品数字标识，无法上架。请编辑商品，在"产品数字标识"专区填写 |
| `50002` | 业务处理失败 / 110250142:该类目要求尺码组件含衣长，请补充后提交（sub_code: isv.business-failed:110250142） | 110250142:该类目要求尺码组件含衣长，请补充后提交 |
| `50002` | 业务处理失败 / 110600000:总店所有店铺商品上限500000，总店中已有500272个上架商品，<span style='color: #FF3B52;'>超出272个</span>，暂时无法上架新的商品，请先下架部分商品，以释放上架额度。（sub_code: isv.business-failed:110600000） | 110600000:总店所有店铺商品上限500000，总店中已有500272个上架商品，<span style='color: #FF3B52;'>超出272个</span>，暂时无法上架新的商品，请先下架部分商品，以释放上架额度。 |
| `50002` | 业务处理失败 / 110101214:商品因处置下架且未修改商品信息，请先修改商品再重新提交上架（sub_code: isv.business-failed:110101214） | 110101214:商品因处置下架且未修改商品信息，请先修改商品再重新提交上架 |
| `50002` | 业务处理失败 / 110101223:商品标题中包含非法字符【&】（sub_code: isv.business-failed:110101223） | 110101223:商品标题中包含非法字符【&】 |

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
  "sub_code": "isv.parameter-invalid:4100003",
  "sub_msg": "参数非法"
}
```

## 备注
