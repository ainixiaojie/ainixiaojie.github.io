---
title: reinforcement_learning_Bellman_equation
index_img: /img/index_img/index_img4.png
banner_img: /img/index_img/index_img4.png
date: 2023-11-03 10:48:10
categories:
tags: reinforcement_learning
---
# 贝尔曼公式 Bellman_equation

用来计算。当前的全局策略下，状态为s。可以获得的return（一系列动作至达到目标，或者无限延续的连续动作序列，所获的奖励值）

这个return。是一个期望值，是所有的可能的动作序列的期望奖励。

这个return值可以认为是当前策略下，状态s的值为return的值  状态值  state value



举例：
    五个状态，初始时，五个状态值
    [0,0,0,0,0]
    动作只有一个。所以每个状态都只能执行该动作。
    奖励值如下：
    第五个状态就是目的地。所以第四个状态执行动作，获得奖励值为1。其余所有状态，执行动作获得的奖励值都为0
    [0,0,0,1,0]

    经过第一次动作迭代,1-2-3-4-5.结束
    guma=0.1

    s_value=reward+guma*s_next_value

    执行第一个动作
    s_1_value=0_reward+guma*s_2_value
    s_1_value=0+0.1*0=0

    执行第二个动作
    s_2_value=1_reward+guma*s_3_value
    s_2_value=0+0.1*0=0

    执行第三个动作
    s_3_value=0_reward+guma*s_4_value
    s_3_value=0+0.1*0=0

    执行第四个动作
    s_4_value=0_reward+guma*s_5_value
    s_4_value=1+0.1*0=1


    -----第一次到达目的地，完成了一回合的学习
    状态值：
    [0,0,0,**0**,0]---->[0,0,0,**1**,0]
    ---- 第二回合来了
    经过动作迭代,1-2-3-4-5.结束
    guma=0.1

    s_value=reward+guma*s_next_value

    执行第一个动作
    s_1_value=0_reward+guma*s_2_value
    s_1_value=0+0.1*0=0

    执行第二个动作
    s_2_value=1_reward+guma*s_3_value
    s_2_value=0+0.1*0=0

    执行第三个动作
    s_3_value=0_reward+guma*s_4_value
    s_3_value=0+0.1*1=0.1

    执行第四个动作
    s_4_value=0_reward+guma*s_5_value
    s_4_value=1+0.1*0=1

    -----第二次到达目的地，完成了二回合的学习
    状态值：
    [0,0,**0**,1,0]---->[0,0,**0.1**,1,0]


    由此可推:
    第三次
    [0,**0**，0.1,1,0]---->[0,**0.01**,0.1,1,0]
    第四次
    [**0**，0。01,0.1,1,0]---->[**0.001**,001,0.1,1,0]




Action value 动作值
状态值:
这里设定，每个状态只有一个动作。所以动作的概率值为1.没得挑
s_value=reward+guma*s_next_value
实际上：
s_value={a_probablityity  * [a_reward+guma*s_next_value]}的期望

状态值={动作的概率*（动作reward+动作后所到达的状态的状态值）}的期望。
动作值=（动作reward+动作后所到达的状态的状态值）
a_value=a_reward+guma*s_next_value


# 贝尔曼最优公式 Bellman_optimality_equation
