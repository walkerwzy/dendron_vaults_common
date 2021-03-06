---
id: 5ca01774-056a-4a48-b815-6eb246e1dd05
title: 水电工程
desc: '装修之水电工程'
updated: 1610126244869
created: 1609762850668
---
## 空气开关
MCB（Miniature Circuit Breaker），短路或用电量超载时会跳闸

## 漏电断路器
现多用二合一型（RCBO，漏电加短路过载保护二合一）
电气设计规范[^1]7.7.10，“家用电器回路与插座回路”要装漏电断路器，等同于“每个回路”要装漏电断路器，但大多数地方都是用空气开关代替了漏电断路器。
如果能严格把照明和插座电路分开，照明回路是可以只需要空气开关的。

识别：
+ 有`RCBO`字样或中文`漏电断路器`字样
+ 个头比空气开关大
+ 有颗黄色的软胶测试按钮（参考储水式热水器上的保护器）
+ 印有vigi的为漏电保护附件，可与空气开关结合，等同漏电断路器

示例：
+ 冰箱1P漏保
+ 监控/网关/传感器/报警器系列，1P漏保
+ 厨房1P漏保
+ 卫生间1P漏保
+ 大功率电器（>2816W[^2]）每个插座分配一个漏保回路（卫生间，厨房按此标准加）
+ 其余插座合为1路用1P漏保

一个漏电断路器16A1P的要`60-120`元，同规格的空气开关约`12-24`元。实在要省成本，厨房，卫生间，工作阳台等近水处，及电热水器，高功率洗烘衣机等用水电器所在回路一定要装。

>不要把漏电断路器装在总开关上。

![](/assets/images/2021-01-04-21-00-33.png)
上图蓝框为三个插座回路三个1P漏保

## 配电箱
一个空气开关1P为1位，普通8-12位，考虑专用回路（如大功率电器，影音回路），不在乎多加点钱上16位，总开关一般就是2P空开，算2位。一个计算示例：

$$
\scriptsize
\begin{array}{c|l|l}
格局/设备 & 回路 &  备注 \\
\hline
空调  &  3回/台 & 每一台空调都要有单独回路 \\
 & & 中央空调单独6mm^2回路 \\
\hline
餐厅厨房 & 2回 & 小家电插座 + 水槽下插座 \\
 & & 大功率电器再加1回 \\
\hline
卫生间 & 1回/间 & 插座、灯具、浴霸共享一回路 \\
 & & 电热水器单独1个回路 \\
\hline
阳台 & 1回 & 洗衣机 \\
\hline
灯具 & 1回 & 房间大或灯具多2回 \\
\hline
插座 & 1回 & 无大功率电器，房间客厅共用1回 \\
 & & 注重音响质量可单占一回 \\
\hline
\bf 总计 & 9-11回 & 配电箱大小为11P+总开关2P=13P 
\end{array}
$$

> 大于2816W算大功率电器[^2]

## 电量电流计算

空开的选择以额定电流**小于**电线的安全载流量为标准，比如1.5mm$^2$电线载流量是13A（国标[^3]523节规定为14.5A），但真到了13A就开始发热了甚至会燃烧，所以在10A时断开是比较安全的。

电流计算： $\scriptsize安培A = 功率瓦数W \div 电压伏特数V$
如果： 电饭锅（3A）+ 微波炉（4A）+ 烤箱（4A）+ 冰箱、榨汁机、灯具等（4A）= 15A，如果再加一台豆浆机（3A），回路就承载了18A，如果机器同时开，16A的空开就会跳闸。

>电气设计规范[^1]： $\scriptsize电器总用电量\leq空开\leq电线$


常见的五孔插座的载流量是`10A`，所以同插座下负载不要过多。千万不要出现一个排插接一个排插挂满负载的情况。孔位是够了，__载流量并不会因为插座变多而变大__。

同一回路上的插座数量不宜超过`10`个，照明回路电流不宜超过`16A`（这也是2.5mm$^2$电线用给照明电路顶天了的原因），光源数量不宜超过`25`个。（电气设计规范[^1]10.7.8， 10.7.9）
参考：
![](/assets/images/2021-01-04-20-57-50.png)

## 电线

电线绝缘皮上会印有制造公司名称与线径截面积，还有最重要的安全认证`CCC`。

绝缘皮的耐用年限约为15-20年，看下制造日期，一定要选择`3年以内`的，避免被人用库存电线、二手电线充数。
关于电线颜色，施工规范[^4]16.14规定：
>配线时，相线与零线的颜色应不同；同一住宅相线（L）颜色应统一，零线（N）宜用$\color{blue}蓝色$，保护线（PE）必须用$\color{olive}黄\color{green}绿$双色线。
> P.S. 相线就是火线，没规定颜色，但全屋必须统一，一般是$\color{red}红色$。

## 地线

配电箱中，会有两排铜排，一个接零线，一个接地线。有的师傅会偷工，不接地线，结果可能会触电。
同样，5孔墙插也最好拆下来看有没有接地线。

## 布线

走线管一般是PVC材质，注意以下原则：

1. 依据施工规范[^4]，一根管子内最多走8条电线
2. 强弱线缆不得穿入同一根管内
3. 强电在上，弱电在下，不平距离不能小于50cm，交叠的地方包锡纸降低干扰
4. 卫生间线管走天花板或墙面
5. 电线与暖气、热水、煤气管间的平行距离不应小于30cm，交叉距离不应小于10cm
6. 线管、接线盒都要固定
7. 留存线管位置图，方便日后维修，或在墙面打孔时提前规避。

## 水管

目前最常见的给水水管材质是PPR（无规共聚聚丙烯Polypropylene-Random)，耐温$70^\circ C$，最高可达$95^\circ C$以上，一米价格`4-9元`，不少品牌还保固50年。

冷水管壁厚2.8~3.5mm，有蓝绿色标示线，热水管约4.2mm，标示线为红色。有预算的话，可全用热水管，参考下图，即选用`D25`规格的管即可（即`6分管`）。
![](/assets/images/2021-01-05-01-11-58.png)

安装水管注意以下原则：

1. 冷热水管距离根据施工规范[^4]15.3.7要求20cm，根据具体情况，也不要小于10cm
2. 水管要用固定环固定好
3. 长距离拉水管，要主干粗，分支细（`D20`，即`4分管`），这是为了末端加压
4. 水管做好当场试水压与漏水
5. 水管埋入墙内冷水管不小于10mm，热水管不小于15mm；埋入地面统一不小心10mm

TIPS：
>+ 水管配件，球阀一定要选活接球阀(下图），建议在厨房洗菜盆下面做一个水管球阀开关！也可以把粗滤过滤器跟球阀装在一起。
+ 进水管加装止水阀，避免跑出去关水表（往往被物业锁了的）
+ 水管可吊装悬挂，方便维修

![](/assets/images/2021-01-05-00-12-19.png)


[^1]:《民用建筑电气设计规范JGJ16-2008》
[^2]: 大功率一般为3200W（16A回路可承受功率），为了安全使用功率会减12%，得2816W 
[^3]:《建筑物电气装置GB/T16895.15》
[^4]:《住宅装饰工程施工规范GB&nbsp;50327-2001》