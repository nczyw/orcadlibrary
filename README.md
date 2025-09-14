# 自用的OrCad的一些库和封装，使用17.4创建的
## 功能说明
 * 重新构建中，会慢慢把以前用过的库更新进来
  
## 焊盘命名规则和钻孔符号
 - 命名规则
   - 贴片方形 : `rx1_0y2_0` : 表示方形焊盘 , x为长度 , y为宽度 ; `c1_0` : 圆形焊盘,1.0表示直径1mm
   - 通孔 : `thru-ic1_0oc2_0` : 1.0为钻孔直径,2.0为焊盘直径 ; `thru-ic1_0orx2_0y3_0` : 1.0钻孔直径,2.0和3.0为焊盘长宽; `thru-2ic1_0oc2_0`:2个钻孔直径为1mm,2.0为圆焊盘直径
   - 槽孔 : `slot-ic1_0oc2_0` : 1.0为槽孔直径,2.0为焊盘直径
 - 通孔槽孔（电镀）: 钻孔符号:`H`
 - 机械孔(非电渡) : 钻孔符号:`N`
 - 过孔 : 钻孔符号:`V`

## 元件制作
 - 添加`User Footprint`属性,为导出BOM表的封装名字
 - 添加`Supplier Part`属性,为供应商内部编号
 - 添加`Purchase link`属性,为采购链接
 - 添加`Datasheet`属性,为元件数据手册

## PDF导出
 - 需要排除一些不必要的选项
 - `Designator`,`Implementation Type`,`Implementation`,`Implementation Path`,`Primitive`

## BOM导出
 - 需要添加的选项
   - 修改:`Footprint`对应值`'{User Footprint}`
   - 添加:`Supplier Part`对应值`'{Supplier Part}`
   - 添加:`Purchase link`对应值`'{Purchase link}`
   - 添加:`Datasheet`对应值`'{Datasheet}`
 - 普通完整指令,不能导出长度超过255长度的属性，否则会截断
   - `Header`:`'Item\t'Quantity\t'Reference\t'Part\t'Footprint\t'Supplier Part`
   - `Combined property string`:`{Item}\t{Quantity}\t'{Reference}\t'{Value}\t'{User Footprint}\t'{Supplier Part}`
 - 嘉立创完整指令,不能导出长度超过255长度的属性，否则会截断
   - `Header`:`'Item\t'Quantity\t'Designator\t'Comment\t'Footprint\t'Supplier Part`
   - `Combined property string`:`{Item}\t{Quantity}\t'{Reference}\t'{Value}\t'{User Footprint}\t'{Supplier Part}`