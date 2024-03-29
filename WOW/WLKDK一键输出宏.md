# <center>WLK3.35PVE_DK一键输出宏(邪冰/传染冰/传染血)

---

### 版主提示：想打出极限DPS，最好还是用手动和一些必备宏配合。对于一键输出宏，适用于一些不是追求极限DPS和WMO冲榜的玩家。

- ##### 如果你不会在出现意外情况(比如暗打被躲闪)的时候手动补循环，请先学习手动循环方法

- 如果你不是工程，则去掉所有的/use 10
- 如果你不是兽人，则去掉所有的/cast 血性狂怒
- 如果你希望手动开饰品及大技能，则去掉所有的/use 10，/use 13，/use 14，/cast 血性狂怒。

- ##### 这里的每一个宏都要打完一个循环再切换，否则会造成严重的乱符文现象！

## 邪冰：

### 单体输出：

#### 邪冰单体输出一句话指南：疾病没了上疾病，鲜血天灾轮流打，符文CD丢缠绕，空闲时间吹号角。

1. 起手：  
```
#showtooltip
/startattack
/castsequence reset=60/combat 暗影打击,冰冷触摸,鲜血打击,天灾打击,鲜血打击,符文武器增效,天灾打击,天灾打击,活力分流,邪恶灵气,召唤石像鬼,鲜血灵气,符文武器增效
/cast [pet] !爪击
/use 10
/use 13
/use 14
/cast 血性狂怒
```
- 这个宏仅在起手时使用一次，一路按到底，到按不动为止。

2. 标准循环：  
```
#showtooltip
/startattack
/castsequence reset=7/combat 暗影打击,冰冷触摸,鲜血打击,天灾打击,鲜血打击,天灾打击,鲜血打击,天灾打击,鲜血打击
/cast !符文打击
/cast [pet] !爪击
/use 10
/use 13
/use 14
/cast 血性狂怒
```
- 无限点这个宏，把凋零缠绕放在这个宏旁边方便看时机扔。

#### 原理如下：

- 第一个10秒循环：暗影打击，冰冷触摸，鲜血打击，天灾打击，鲜血打击，凋零缠绕xN。
- 第二个10秒循环：天灾打击，鲜血打击，天灾打击，鲜血打击，凋零缠绕xN。
- 如此反复即为邪冰的标准单体循环。

### AOE输出：

- 宏  
```
#showtooltip
/startattack
/castsequence reset=7/combat 暗影打击,冰冷触摸,传染,!枯萎凋零,天灾打击,鲜血打击,天灾打击,血液沸腾
/cast [button:2]!符文打击
/petattack
```
- 无限点这个宏，把凋零缠绕放在这个宏旁边方便看时机扔。

#### 原理如下：
- 第一个10秒循环：暗影打击，冰冷触摸，传染，枯萎凋零，凋零缠绕xN。
- 第二个10秒循环：天灾打击，鲜血打击，天灾打击，血沸，凋零缠绕xN。
- 如此反复即为邪冰的标准AOE循环。

### 如果你是邪冰，请养成先打暗打再打冰触的好习惯，不要以任何理由先上冰触。

## 传染冰：

### 使用说明：
1. 开场连续猛击宏1，直到你看到一个5分钟的CD为止，然后使用冰霜打击/免费凛风冲击来消耗你的符文能量。
2. 然后连点宏2，直到看到CD为止，再使用冰霜打击/免费凛风冲击来消耗你的符文能量。重复这个过程，也就是宏1-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风……
3. 过了一段时间(确切的来说，是4个"宏2-冰打凛风"的循环)，你会发现宏2变成了鲜血灵气的图标，点不动了！
4. 这个时候请果断转用宏3，也就是宏3-冰打凛风-宏3-冰打凛风-(到这里你会发现宏3也点不动了)。
5. 然后就可以转回宏2-冰打凛风的过程了，如上反复循环。

##### 全程不断病的情况下输出应该是这样的：
宏1-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏3-冰打凛风-宏3-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏3-冰打凛风-宏3-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏3-冰打凛风-宏3-冰打凛风………………

##### 如果你断疾病了，则按以下顺序来打：
断疾病-宏4点到显示鲜血灵气点不动为止-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏2-冰打凛风-宏3-冰打凛风-宏3-冰打凛风………………

#### 请注意一点：公共CD是十分紧张的，你应当保证只要宏2/宏3亮着就能立刻打出去！控制你的技能数量，不要贪太多冰打和免费凛风。

#### 如果杀戮机器和免费凛风同时触发了，则先打冰打，再打免费凛风。

### 宏：
- 冰打宏(请将这个宏用来代替你的冰霜打击技能)  
```
#showtooltip
/cancelaura 活力分流
/cast 冰霜打击
/cast !符文打击
```

#### 第一种

1. 起手  
```
#showtooltip
/startattack
/castsequence reset=60/combat 冰冷触摸,暗影打击,铜墙铁壁,活力分流,湮没,传染,符文武器增效,湮没,湮没,冰霜打击,湮没,亡者复生,符文武器增效
/cast 血性狂怒
/use 10
/use 13
/use 14
/use 速度药水
```
2. 正常循环  
```
#showtooltip
/startattack
/castsequence reset=7/combat 湮没,湮没,冰霜打击,鲜血打击,传染,湮没,湮没,冰霜打击,湮没,湮没,湮没,冰霜打击,鲜血打击,传染,湮没,湮没,冰霜打击,湮没,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```
3. 插入铜墙铁壁  
```
#showtooltip
/startattack
/castsequence reset=7/combat 湮没,湮没,冰霜打击,鲜血打击,传染,湮没,湮没,冰霜打击,铜墙铁壁,活力分流,湮没,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```
4. 断疾病后的补病循环  
```
#showtooltip
/startattack
/castsequence reset=7/combat/target 冰冷触摸,暗影打击,湮没,冰霜打击,鲜血打击,传染,冰霜打击,湮没,湮没,冰霜打击,湮没,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```

#### 第二种

1. 起手  
```
#showtooltip
/startattack
/castsequence reset=60/combat 冰冷触摸,暗影打击,活力分流,铜墙铁壁,冰霜打击,湮没,传染,亡者复生,冰霜打击,符文武器增效,符文武器增效
/cast 血性狂怒
/use 10
/use 13
/use 14
/use 速度药水
```
2. 正常循环  
```
#showtooltip
/startattack
/castsequence reset=7/combat 湮没,湮没,湮没,湮没,湮没,鲜血打击,传染,湮没,湮没,湮没,湮没,湮没,鲜血打击,传染,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```
3. 插入铜墙铁壁  
```
#showtooltip
/startattack
/castsequence reset=7/combat 湮没,湮没,湮没,湮没,湮没,冰霜打击,活力分流,铜墙铁壁,传染,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```
4. 断疾病后的补病循环  
```
#showtooltip
/startattack
/castsequence reset=7/combat/target 冰冷触摸,暗影打击,湮没,鲜血打击,传染,鲜血灵气
/cast !符文打击
/cast 血性狂怒
/use 10
/use 13
/use 14
```

## 传染血：

### 使用说明
- 连续点宏1起手，点不动之后无限点宏2即可，其他什么都不要点。

### 宏

1. 起手  
```
#showtooltip
/startattack
/castsequence reset=7/combat 冰冷触摸,暗影打击,灵界打击,亡者复生,寒冬号角,心脏打击,心脏打击,凋零缠绕,灵界打击,心脏打击,心脏打击,凋零缠绕,心脏打击,传染,鲜血灵气
/use 10
/use 13
/use 14
/cast 血性狂怒
```
2. 正常循环  
```
#showtooltip
/startattack
/castsequence reset=7/combat 心脏打击,心脏打击,灵界打击,凋零缠绕,心脏打击,心脏打击,凋零缠绕,灵界打击,心脏打击,心脏打击,凋零缠绕,心脏打击,传染,心脏打击,心脏打击,灵界打击,凋零缠绕,心脏打击,心脏打击,凋零缠绕,灵界打击,心脏打击,心脏打击,寒冬号角,心脏打击,传染
/use 10
/use 13
/use 14
```

