## 这是啥

试图发现三国人物之间的依赖关系——扯淡——这是手游《放开那三国》武将羁绊的关系图。

## 什么是武将羁绊

游戏中上阵只能是主角+五个三国人物，为了让游戏内容更加丰富，设定当人物之间符合特定关系时，能激发出攻击加强、防御加强、生命值增加等特效。

比如，凑齐了`吕布`+`貂蝉`，就会触发`英雄美人：吕布和貂蝉同时上场，攻击+27%`的羁绊特效。

![吕布-貂蝉](img/lb-dc.png)

双方都得到加强，是极好的。

但是很多时候羁绊是单向的：如`关羽`能够为`关索`增加`荆州认父：攻击+23%`的效果，但是`关索`上场不能增益`关羽`的属性——大概是`领袖光环`吧。

而且，游戏策划为了让事情更复杂，还有群体羁绊，如`五虎上将（关羽、张飞、赵云、马超、黄忠）同时上场，攻击+32%，生命+32%`。

## 怎么实现

将武将当做模块，用requirejs描述模块关系，madge形成模块依赖图。

## 为什么要搞这么个东西

因为蛋疼。

这一套体系在手游中非常流行，`我叫MT`中称为`组合`，`暴走武侠`中称为`缘分`，实质都是一样的。我想定量看看这些策划是怎么想的。

## 大概是个啥效果

![三国](img/sanguo.png)

## 原来是啥样子

<table width="450" align="center" border="0">
    <tbody align="center">
        <tr>
            <td rowspan="3">
            <div align="center"><strong>刘备</strong></div>
            </td>
            <td><strong>孙尚香</strong></td>
            <td colspan="2">娶我可好：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>法正</strong></td>
            <td colspan="2">雄才大略：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>孟获、祝融</strong></td>
            <td colspan="2">蜀入西川：同时上场，攻击+28%</td>
        </tr>
        <tr>
            <td rowspan="3"><strong>孟获</strong></td>
            <td><strong>诸葛亮</strong></td>
            <td colspan="2">七擒七纵：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>关兴</strong></td>
            <td colspan="2">勇猛非常：<a target="_blank" href="http://www.youba.com/wangyou/fangkainasanguo/yxtj/qx/wu/1401/31386/1.htm"></a>同时上场，生命+21%</td>
        </tr>
        <tr>
            <td><strong>刘备、祝融</strong></td>
            <td colspan="2">蜀入西川：同时上场，攻击+28%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>诸葛亮</strong></td>
            <td><strong>孟获</strong></td>
            <td colspan="2">七擒七纵：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>法正</strong></td>
            <td colspan="2">取长补短：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>刘备、赵云</strong></td>
            <td colspan="2">共扶汉室：同时上场，攻击+35%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>祝融</strong></td>
            <td><strong>关银萍</strong></td>
            <td colspan="2">自幼习武：同时上场，生命+21%</td>
        </tr>
        <tr>
            <td><strong>夏侯氏</strong></td>
            <td colspan="2">女中豪杰：同时上场，攻击+20%</td>
        </tr>
        <tr>
            <td><strong>刘备、孟获</strong></td>
            <td colspan="2">蜀入西川：同时上场，攻击+28%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>关索</strong></td>
            <td><strong>关羽</strong></td>
            <td colspan="2">荆州认父：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>关银萍</strong></td>
            <td colspan="2">兄妹连襟：同时上场，生命+21%</td>
        </tr>
        <tr>
            <td><strong>费祎</strong></td>
            <td colspan="2">侠肝义胆：同时上场，生命+23%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>姜维</strong></td>
            <td><strong>张飞</strong></td>
            <td colspan="2">有胆有谋：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>太史慈</strong></td>
            <td colspan="2">继承遗志：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>华佗、甄姬</strong></td>
            <td colspan="2">钻研医术：同时上场，防御+42%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>马谡</strong></td>
            <td><strong>诸葛亮</strong></td>
            <td colspan="2">错失街亭：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>姜维</strong></td>
            <td colspan="2">好论军计：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>严颜</strong></td>
            <td colspan="2">严肃点儿：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>夏侯氏</strong></td>
            <td><strong>祝融</strong></td>
            <td colspan="2">女中豪杰：同时上场，攻击+20%</td>
        </tr>
        <tr>
            <td><strong>张绣</strong></td>
            <td colspan="2">谋而后动：同时上场，攻击+19%</td>
        </tr>
        <tr>
            <td><strong>卞氏、王异</strong></td>
            <td colspan="2">声色谋生：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>魏延</strong></td>
            <td><strong>关羽</strong></td>
            <td colspan="2">武神附体：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>张飞</strong></td>
            <td colspan="2">狂战天下：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>典韦、许褚</strong></td>
            <td colspan="2">巍然不动：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>黄忠</strong></td>
            <td><strong>黄盖</strong></td>
            <td colspan="2">老当益壮：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>鲁肃</strong></td>
            <td colspan="2">我有这箭：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>关羽、张飞、赵云、马超</strong></td>
            <td colspan="2">五虎上将：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>徐庶</strong></td>
            <td><strong>左慈</strong></td>
            <td colspan="2">丹鼎道术：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>张春华</strong></td>
            <td colspan="2">天文数理：同时上场，生命+23%</td>
        </tr>
        <tr>
            <td><strong>貂蝉、黄月英</strong></td>
            <td colspan="2">九曲连环：同时上场，生命+36%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>黄月英</strong></td>
            <td><strong>赵云</strong></td>
            <td colspan="2">龙应双翼：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>蔡文姬</strong></td>
            <td colspan="2">急中生智：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>貂蝉、徐庶</strong></td>
            <td colspan="2">九曲连环：同时上场，生命+36%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>关羽</strong></td>
            <td><strong>华佗</strong></td>
            <td colspan="2">刮骨疗伤：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>魏延</strong></td>
            <td colspan="2">武神附体：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>张飞、赵云、马超、黄忠</strong></td>
            <td colspan="2">五虎上将：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>张飞</strong></td>
            <td><strong>姜维</strong></td>
            <td colspan="2">有胆有谋：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>魏延</strong></td>
            <td colspan="2">狂战天下：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>关羽、赵云、马超、黄忠</strong></td>
            <td colspan="2">五虎上将：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>赵云</strong></td>
            <td><strong>黄月英</strong></td>
            <td colspan="2">龙应双翼：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>法正</strong></td>
            <td colspan="2">大义为重：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>关羽、张飞、马超、黄忠</strong></td>
            <td colspan="2">五虎上将：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>马超</strong></td>
            <td><strong>曹仁</strong></td>
            <td colspan="2">你攻我守：同时上场，生命+30%</td>
        </tr>
        <tr>
            <td><strong>太史慈</strong></td>
            <td colspan="2">信布之勇：同时上场，攻击+24%</td>
        </tr>
        <tr>
            <td><strong>关羽、张飞、赵云、黄忠</strong></td>
            <td colspan="2">五虎上将：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>法正</strong></td>
            <td><strong>赵云</strong></td>
            <td colspan="2">大义为重：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>诸葛亮</strong></td>
            <td colspan="2">取长补短：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>刘备</strong></td>
            <td colspan="2">雄才大略：同时上场，生命+26%</td>
        </tr>
    </tbody>
</table>

<table width="450" align="center" border="0">
    <tbody align="center">
        <tr>
            <td rowspan="3">
            <div align="center"><strong>曹仁</strong></div>
            </td>
            <td><strong>马超</strong></td>
            <td colspan="2">你攻我守：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>于禁</strong></td>
            <td colspan="2">铜墙铁壁：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>典韦、华雄</strong></td>
            <td colspan="2">血煞溃围：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td rowspan="3"><strong>许褚</strong></td>
            <td><strong>徐晃</strong></td>
            <td colspan="2">食神助我：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>高顺</strong></td>
            <td colspan="2">勇力绝人：<a target="_blank" href="http://www.youba.com/wangyou/fangkainasanguo/yxtj/qx/wu/1401/31386/1.htm"></a>同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>典韦、魏延</strong></td>
            <td colspan="2">巍然不动：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>郭嘉</strong></td>
            <td><strong>曹操</strong></td>
            <td colspan="2">夜思奉孝：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>甄姬</strong></td>
            <td colspan="2">鬼惊神惧：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>夏侯惇、徐晃</strong></td>
            <td colspan="2">鬼神莫测：同时上场，攻击+33%</td>
        </tr>
        <tr>
            <td  rowspan="4"><strong>典韦</strong></td>
            <td><strong>徐晃</strong></td>
            <td colspan="2">古煞恶来：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>曹丕</strong></td>
            <td colspan="2">面不改色：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>曹仁、华雄</strong></td>
            <td colspan="2">血煞溃围：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td><strong>魏延、许褚</strong></td>
            <td colspan="2">巍然不动&nbsp;：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>夏侯惇</strong></td>
            <td><strong>貂蝉</strong></td>
            <td colspan="2">孤狼之月：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>张郃</strong></td>
            <td colspan="2">开国元勋：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>郭嘉、徐晃</strong></td>
            <td colspan="2">鬼神莫测：同时上场，攻击+33%</td>
        </tr>
        <tr>
            <td  rowspan="4"><strong>徐晃</strong></td>
            <td><strong>典韦</strong></td>
            <td colspan="2">古煞恶来：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>许褚</strong></td>
            <td colspan="2">食神助我：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>张辽、张郃、乐进、于禁</strong></td>
            <td colspan="2">五子良将：同时上场，生命+30%，攻击+30%</td>
        </tr>
        <tr>
            <td><strong>夏侯惇、郭嘉</strong></td>
            <td colspan="2">鬼神莫测：同时上场，攻击+33%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>于禁</strong></td>
            <td><strong>曹仁</strong></td>
            <td colspan="2">铜墙铁壁：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>满宠</strong></td>
            <td colspan="2">屡有功劳：同时上场，生命+23%</td>
        </tr>
        <tr>
            <td><strong>徐晃、张郃、乐进、张辽</strong></td>
            <td colspan="2">五子良将：同时上场，生命+30%，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>张郃</strong></td>
            <td><strong>夏侯惇</strong></td>
            <td colspan="2">开国元勋：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>袁绍</strong></td>
            <td colspan="2">我不听你：同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>张辽、徐晃、乐进、于禁</strong></td>
            <td colspan="2">五子良将：同时上场，生命+30%，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>乐进</strong></td>
            <td><strong>曹洪</strong></td>
            <td colspan="2">虎狼之师：同时上场，生命+23%</td>
        </tr>
        <tr>
            <td><strong>曹昂</strong></td>
            <td colspan="2">胆识英烈：同时上场，生命+19%</td>
        </tr>
        <tr>
            <td><strong>张辽、徐晃、张郃、于禁</strong></td>
            <td colspan="2">五子良将：同时上场，生命+30%，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>甄姬</strong></td>
            <td><strong>郭嘉</strong></td>
            <td colspan="2">鬼惊神惧：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td><strong>曹丕</strong></td>
            <td colspan="2">文昭魏后：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>华佗、姜维</strong></td>
            <td colspan="2">钻研医术：同时上场，防御+42%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>杨修</strong></td>
            <td><strong>郭嘉</strong></td>
            <td colspan="2">学问渊博：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>曹操</strong></td>
            <td colspan="2">来食鸡肋：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>司马昭</strong></td>
            <td colspan="2">只待烧鸡：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>蔡文姬</strong></td>
            <td><strong>黄月英</strong></td>
            <td colspan="2">急中生智：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>文丑</strong></td>
            <td colspan="2">文丑人美：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>甘夫人、步练师</strong></td>
            <td colspan="2">忠贞不渝：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>曹操</strong></td>
            <td><strong>张辽</strong></td>
            <td colspan="2">赤壁鏖兵：同时上场，生命+30%</td>
        </tr>
        <tr>
            <td><strong>郭嘉</strong></td>
            <td colspan="2">夜思奉孝：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>曹丕、司马懿</strong></td>
            <td colspan="2">俊杰奇韬：同时上场，生命+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>司马懿</strong></td>
            <td><strong>张辽</strong></td>
            <td colspan="2">卓尔不群：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td><strong>贾诩</strong></td>
            <td colspan="2">心狠手辣：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>曹丕、曹操</strong></td>
            <td colspan="2">俊杰奇韬：同时上场，生命+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>曹丕</strong></td>
            <td><strong>典韦</strong></td>
            <td colspan="2">面不改色：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>甄姬</strong></td>
            <td colspan="2">文昭魏后：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>曹操、司马懿</strong></td>
            <td colspan="2">俊杰奇韬：同时上场，生命+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>张辽</strong></td>
            <td><strong>曹操</strong></td>
            <td colspan="2">赤壁鏖兵：同时上场，生命+30%</td>
        </tr>
        <tr>
            <td><strong>司马懿</strong></td>
            <td colspan="2">卓尔不群：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td><strong>张郃、徐晃、乐进、于禁</strong></td>
            <td colspan="2">五子良将：同时上场，生命+30%，攻击+30%</td>
        </tr>
    </tbody>
</table>

<table width="450" align="center" border="0">
    <tbody align="center">
        <tr>
            <td rowspan="3">
            <div align="center"><strong>孙权</strong></div>
            </td>
            <td><strong>吕蒙</strong></td>
            <td colspan="2">刮目相看：同时上场，防御+32%</td>
        </tr>
        <tr>
            <td><strong>徐盛</strong></td>
            <td colspan="2">招贤纳士：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>孙策、甘宁</strong></td>
            <td colspan="2">一身正气：同时上场，生命+39%</td>
        </tr>
        <tr>
            <td rowspan="3"><strong>太史慈</strong></td>
            <td><strong>马超</strong></td>
            <td colspan="2">信布之勇：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>姜维</strong></td>
            <td colspan="2">勇力绝人：<a target="_blank" href="http://www.youba.com/wangyou/fangkainasanguo/yxtj/qx/wu/1401/31386/1.htm"></a>同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>周瑜、孙坚、甘宁、吕蒙</strong></td>
            <td colspan="2">江东柱石：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>孙策</strong></td>
            <td><strong>黄盖</strong></td>
            <td colspan="2">江东霸王：同时上场，生命+28%</td>
        </tr>
        <tr>
            <td><strong>大乔</strong></td>
            <td colspan="2">伉俪情深：同时上场，防御+34%</td>
        </tr>
        <tr>
            <td><strong>孙权、甘宁</strong></td>
            <td colspan="2">一身正气：同时上场，生命+39%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>孙坚</strong></td>
            <td><strong>孙权</strong></td>
            <td colspan="2">孙氏父子：同时上场，防御+30%</td>
        </tr>
        <tr>
            <td><strong>孙尚香</strong></td>
            <td colspan="2">孙氏父女：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>太史慈、周瑜、甘宁、吕蒙</strong></td>
            <td colspan="2">江东柱石：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>吕蒙</strong></td>
            <td><strong>陆逊</strong></td>
            <td colspan="2">胸怀宽广：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>孙权</strong></td>
            <td colspan="2">刮目相看：同时上场，防御+32%</td>
        </tr>
        <tr>
            <td><strong>太史慈、周瑜、甘宁、孙坚</strong></td>
            <td colspan="2">江东柱石：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="4"><strong>甘宁</strong></td>
            <td><strong>鲁肃</strong></td>
            <td colspan="2">江东基业：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>徐盛</strong></td>
            <td colspan="2">奇袭荆州：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>太史慈、周瑜、吕蒙、孙坚</strong></td>
            <td colspan="2">江东柱石：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td><strong>孙策、孙权</strong></td>
            <td colspan="2">一身正气：同时上场，生命+39%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>周瑜</strong></td>
            <td><strong>小乔</strong></td>
            <td colspan="2">郎才女貌：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>陆逊</strong></td>
            <td colspan="2">我是都督：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>太史慈、甘宁、吕蒙、孙坚</strong></td>
            <td colspan="2">江东柱石：同时上场，攻击+32%，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>徐盛</strong></td>
            <td><strong>甘宁</strong></td>
            <td colspan="2">奇袭荆州：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>孙权</strong></td>
            <td colspan="2">招贤纳士：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>周泰、陆抗</strong></td>
            <td colspan="2">出生入死：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="4"><strong>周泰</strong></td>
            <td><strong>张昭</strong></td>
            <td colspan="2">新秀元老：同时上场，防御+27%</td>
        </tr>
        <tr>
            <td><strong>凌统</strong></td>
            <td colspan="2">胆色绝伦：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>程普</strong></td>
            <td colspan="2">激昂作战：同时上场，防御+28%</td>
        </tr>
        <tr>
            <td><strong>徐盛、陆抗</strong></td>
            <td colspan="2">出生入死：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>鲁肃</strong></td>
            <td><strong>甘宁</strong></td>
            <td colspan="2">江东基业：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>黄忠</strong></td>
            <td colspan="2">我这有箭：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>陆逊、周瑜</strong></td>
            <td colspan="2">好为奇计：同时上场，生命+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>陆逊</strong></td>
            <td><strong>周瑜</strong></td>
            <td colspan="2">我是都督：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>吕蒙</strong></td>
            <td colspan="2">胸怀宽广：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>周瑜、鲁肃</strong></td>
            <td colspan="2">好为奇计：同时上场，生命+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>大乔</strong></td>
            <td><strong>孙策</strong></td>
            <td colspan="2">伉俪情深：同时上场，防御+34%</td>
        </tr>
        <tr>
            <td><strong>步练师</strong></td>
            <td colspan="2">国色天香：同时上场，防御+25%</td>
        </tr>
        <tr>
            <td><strong>小乔、孙尚香</strong></td>
            <td colspan="2">襟怀坦白：同时上场，防御+41%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>小乔</strong></td>
            <td><strong>周瑜</strong></td>
            <td colspan="2">郎才女貌：同时上场，生命+34%</td>
        </tr>
        <tr>
            <td><strong>步练师</strong></td>
            <td colspan="2">性格温和：同时上场，防御+25%</td>
        </tr>
        <tr>
            <td><strong>大乔、孙尚香</strong></td>
            <td colspan="2">襟怀坦白：同时上场，防御+41%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>孙尚香</strong></td>
            <td><strong>刘备</strong></td>
            <td colspan="2">娶我可好：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>孙坚</strong></td>
            <td colspan="2">孙氏父女：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>大乔、小乔</strong></td>
            <td colspan="2">襟怀坦白：同时上场，防御+41%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>黄盖</strong></td>
            <td><strong>孙策</strong></td>
            <td colspan="2">江东霸王：同时上场，生命+28%</td>
        </tr>
        <tr>
            <td><strong>黄忠</strong></td>
            <td colspan="2">老当益壮：同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>张昭、凌统</strong></td>
            <td colspan="2">刚正不阿：同时上场，生命+27%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>丁奉</strong></td>
            <td><strong>凌操</strong></td>
            <td colspan="2">雪中奋兵：同时上场，生命+23%</td>
        </tr>
        <tr>
            <td><strong>潘璋</strong></td>
            <td colspan="2">年少骁勇：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>朱桓</strong></td>
            <td colspan="2">奋勇杀敌：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>潘璋</strong></td>
            <td><strong>凌操</strong></td>
            <td colspan="2">扫除奸佞：同时上场，攻击+20%</td>
        </tr>
        <tr>
            <td><strong>丁奉</strong></td>
            <td colspan="2">年少骁勇：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>朱桓</strong></td>
            <td colspan="2">斩将夺旗：同时上场，攻击+21%</td>
        </tr>
    </tbody>
</table>

<table border="0" width="450" align="center">
    <tbody align="center">
        <tr>
            <td  rowspan="3">
            <div align="center"><strong>袁绍</strong></div>
            </td>
            <td><strong>张郃</strong></td>
            <td colspan="2">我不听你：同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>董卓</strong></td>
            <td colspan="2">烽烟四起：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>袁术</strong></td>
            <td colspan="2">四世三公：同时上场，攻击+19%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>颜良</strong></td>
            <td><strong>文丑</strong></td>
            <td colspan="2">同生共死：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>陈宫</strong></td>
            <td colspan="2">智勇双全：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>纪灵</strong></td>
            <td colspan="2">袁家大将：同时上场，攻击+19%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>文丑</strong></td>
            <td><strong>颜良</strong></td>
            <td colspan="2">同生共死：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>华雄</strong></td>
            <td colspan="2">拔剑擎刀：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>蔡文姬</strong></td>
            <td colspan="2">文丑人美：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>于吉</strong></td>
            <td><strong>张角</strong></td>
            <td colspan="2">太平要术：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>陈登</strong></td>
            <td colspan="2">屡有功劳：同时上场，生命+28%</td>
        </tr>
        <tr>
            <td><strong>左慈、诸葛亮</strong></td>
            <td colspan="2">呼风唤雨：同时上场，攻击+38%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>华佗</strong></td>
            <td><strong>关羽</strong></td>
            <td colspan="2">刮骨疗伤：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>贾诩</strong></td>
            <td colspan="2">神农百草：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>甑姬、姜维</strong></td>
            <td colspan="2">钻研医术：同时上场，防御+42%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>貂蝉</strong></td>
            <td><strong>夏侯惇</strong></td>
            <td colspan="2">孤狼卫月：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>吕布</strong></td>
            <td colspan="2">英雄美人：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>徐庶、黄月英</strong></td>
            <td colspan="2">九曲连环：同时上场，生命+36%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>华雄</strong></td>
            <td><strong>文丑</strong></td>
            <td colspan="2">拔剑擎刀：同时上场，攻击+23%</td>
        </tr>
        <tr>
            <td><strong>董卓</strong></td>
            <td colspan="2">虎体狼腰：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>典韦、曹仁</strong></td>
            <td colspan="2">血煞溃围：同时上场，攻击+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>陈宫</strong></td>
            <td><strong>吕布</strong></td>
            <td colspan="2">如虎添翼：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>颜良</strong></td>
            <td colspan="2">智勇双全：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>高顺、陈登</strong></td>
            <td colspan="2">谦虚谨慎：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>陈登</strong></td>
            <td><strong>于吉</strong></td>
            <td colspan="2">蛊惑人心：同时上场，生命+28%</td>
        </tr>
        <tr>
            <td><strong>李儒</strong></td>
            <td colspan="2">为人爽朗：同时上场，攻击+19%</td>
        </tr>
        <tr>
            <td><strong>高顺、陈宫</strong></td>
            <td colspan="2">谦虚谨慎：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>高顺</strong></td>
            <td><strong>许褚</strong></td>
            <td colspan="2">勇力绝人：同时上场，攻击+21%</td>
        </tr>
        <tr>
            <td><strong>刘表</strong></td>
            <td colspan="2">六六大顺：同时上场，生命+21%</td>
        </tr>
        <tr>
            <td><strong>陈宫、陈登</strong></td>
            <td colspan="2">谦虚谨慎：同时上场，生命+32%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>董卓</strong></td>
            <td><strong>华雄</strong></td>
            <td colspan="2">虎体狼腰：同时上场，生命+26%</td>
        </tr>
        <tr>
            <td><strong>袁绍</strong></td>
            <td colspan="2">烽烟四起：同时上场，生命+24%</td>
        </tr>
        <tr>
            <td><strong>吕布、贾诩、丁原、张角</strong></td>
            <td colspan="2">乱世天下：同时上场，攻击+30%，生命+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>张角</strong></td>
            <td><strong>左慈</strong></td>
            <td colspan="2">妖邪当道：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>于吉</strong></td>
            <td colspan="2">太平要术：同时上场，攻击+29%</td>
        </tr>
        <tr>
            <td><strong>吕布、贾诩、丁原、董卓</strong></td>
            <td colspan="2">乱世天下：同时上场，攻击+30%，生命+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>吕布</strong></td>
            <td><strong>陈宫</strong></td>
            <td colspan="2">如虎添翼：同时上场，攻击+25%</td>
        </tr>
        <tr>
            <td><strong>貂蝉</strong></td>
            <td colspan="2">英雄美人：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>张角、贾诩、丁原、董卓</strong></td>
            <td colspan="2">乱世天下：同时上场，攻击+30%，生命+30%</td>
        </tr>
        <tr>
            <td  rowspan="3"><strong>贾诩</strong></td>
            <td><strong>司马懿</strong></td>
            <td colspan="2">心狠手辣：同时上场，攻击+27%</td>
        </tr>
        <tr>
            <td><strong>贾诩</strong></td>
            <td colspan="2">神农百草：同时上场，生命+29%</td>
        </tr>
        <tr>
            <td><strong>张角、吕布、丁原、董卓</strong></td>
            <td colspan="2">乱世天下：同时上场，攻击+30%，生命+30%</td>
        </tr>
    </tbody>
</table>





