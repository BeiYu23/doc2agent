# shop.marketCategoryOperate

> 店铺装修类目操作接口

| 元信息 | 值 |
| --- | --- |
| 接口 ID | `doudian.decoration.shop.marketCategoryOperate` |
| 中文名 | 店铺装修类目操作 |
| 平台 | `doudian` |
| 请求方法 | `GET` |
| 接口路径 | `/shop/marketCategoryOperate` |
| Base URL | `https://openapi-fxg.jinritemai.com` |
| 鉴权方式 | `access_token+sign` |
| 文档来源 | https://op.jinritemai.com/docs/api-docs/167/2903 |
| 更新日期 | `2024-11-21` |

## 接口说明

- 文档书: 店铺装修API（版本 V2.01）
- 公共参数（method/app_key/access_token/param_YOUR_SECRET_KEY_method）见 doudian/agent/_common.json

## 请求参数

| 参数名 | 位置 | 类型 | 必填 | 说明 | 示例 |
| --- | --- | --- | --- | --- | --- |
| `operate_type` | body | string | 是 | 操作类型：创建、更新、删除  1. create创建：category_id parent_category_id 只有以下两种情况（0等同于nil）: nil nil 表示创建一个一级分类， nil parent_category_id 表示在指定一级分类下创建一个二级分类；  2. update编辑：category_id parent_category_id  只有以下两种情况： categoryId nil 表示编辑一个一级分类， categoryId parent_category_id 表示编辑一个二级分类；  3. delete删除：category_id parent_category_id 只有以下两种情况： category_id nil 表示删除一个一级分类及关联二级分类.(含商品) category_id parent_category_id  表示删除一个二级分类； | `create、update、delete` |
| `parent_category_id` | body | mixed | 否 | 父类目的id，传0或者不传则category_id表示一级类目 | `7184332308881850668` |
| `category_id` | body | mixed | 否 | 类目的id,创建的时候不传或传0，编辑删除的时候必传 | `7184332308881850668` |
| `sequence` | body | mixed | 否 | 表示类目在同级别排序的索引位置（从0开始），-1表示倒数第一，-2倒数第二，以此类推。不传则不变化（create时默认后面追加,修改顺序请使用update方法）。 如3个一级分类，取值范围[-2,2]。注意：0也是有效值 | `1` |
| `category_name` | body | string | 否 | 类目名称，创建操作时必填名称 | `水果生鲜` |
| `rank` | body | mixed | 否 | 类目在同级别优先级权重，越大则越靠前，范围[0,100000]，若指定sequence，则rank失效 | `5000` |
| `tmp_id` | body | mixed | 否 | 要更新的页面，如果存在多个生效页面，必须指定。可以从管理端查询，或通过[/shop/openShopPageManagementList]接口查询。 | `页面ID` |

## 请求示例

```bash
curl -X GET 'https://openapi-fxg.jinritemai.com/shop/marketCategoryOperate?app_key=your_appkey_here&method=shop.marketCategoryOperate&access_token=your_accesstoken_here&param_json={}&timestamp=2018-06-19%2016:06:59&v=2&sign=your_sign_here'
```

## 响应参数

| 字段名 | 类型 | 说明 | 示例 |
| --- | --- | --- | --- |
| `category_id` | mixed | 创建、编辑、删除的类目id。 创建成功后进入审核阶段，正式生效存在秒级时差。 | `7184332308881850668` |

## 响应码

| code | 含义 | 处理建议 |
| --- | --- | --- |
| `10000` | success | 正常处理 |
| `40004` | 非法的参数 / 参数检验不通过（sub_code: isv.parameter-invalid:20115） | 请检查参数是否合法，是否是有效的类目信息 |
| `50002` | 业务处理失败 / 系统异常（sub_code: isv.business-failed:20116） | 处理失败，请重试或联系客服处理 |
| `50002` | 业务处理失败 / 参数检验不通过（sub_code: isv.business-failed:20120） | 请检查参数是否合法，是否是有效的类目信息 |
| `50002` | 业务处理失败 / 参数为空，请检查（sub_code: isv.business-failed:10000） | 请检查参数是否符合规范 |
| `50002` | 业务处理失败 / 参数检验不通过（sub_code: isv.business-failed:20125） | 请检查参数是否合法，是否是有效的类目信息 |
| `50002` | 业务处理失败 / 当前页面处于[待送审], 不可编辑（sub_code: isv.business-failed:20000） | 当前页面送审中，请延迟稍后再试。 |
| `50002` | 业务处理失败 / 分类ID未查询到有效类目（sub_code: isv.business-failed:20130） | 分类ID不存在，或分类未正式生效，先调用查询接口，待生效后操作。 |
| `50002` | 业务处理失败 / 系统异常，请联系客服咨询（sub_code: isv.business-failed:50012） | 系统异常，联系客服 |
| `50002` | 业务处理失败 / 当前页面未生效（sub_code: isv.business-failed:20110） | 页面未生效，请先到PC后台将页面发布 |
| `50002` | 业务处理失败 / 网络异常，请稍后重试（sub_code: isv.business-failed:20126） | 系统异常，联系客服 |
| `50002` | 业务处理失败 / 存在多个生效的页面,请指定id（sub_code: isv.business-failed:23000） | 存在多个生效的页面，需要指定tmp_id |
| `50002` | 业务处理失败 / 没有可编辑的分类页版本，请到商家后台创建并生效（sub_code: isv.business-failed:20111） | 当前没有生效的分类页，请先到pc后台创建 |
| `50002` | 业务处理失败 / 61000:当前层级含29个分类,sequence有效范围[-28,28]（sub_code: isv.business-failed:61000） | 再更新的时候，sequence超过有效范围 |
| `50002` | 业务处理失败 / 23001:名称不能包含'爆款推荐'（sub_code: isv.business-failed:23001） | 名称不能包含“推荐”等关键词 |
| `50002` | 业务处理失败 / 30002:当前页面无组件，不允许生效（sub_code: isv.business-failed:30002） | 需要先创建一个分类 |

## 响应示例

成功：

```json
{
  "data": {
    "category_id": "7184332308881850668"
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
  "sub_code": "isv.parameter-invalid:20115",
  "sub_msg": "参数检验不通过"
}
```

## 备注
