# 自用的OrCad的一些库和封装，使用17.4创建的
## 功能说明
 * 重新构建中，会慢慢把以前用过的库更新进来

## 元件制作
 - 添加`User Footprint`属性,为导出BOM表的封装名字
 - 添加`Buy`属性,为供应商数据
 - 添加`Datasheet`属性,为元件数据手册

## BOM导出
 - 修改:`Footprint`对应值`'{User Footprint}`
 - 添加:`Supplier Part`对应值`'{Buy}`
 - 添加:`Datasheet`对应值`'{Datasheet}`