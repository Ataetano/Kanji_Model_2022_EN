## Introduction
This mathematical model is designed to analyze the results of kanji learning, the time it takes to learn kanji characters, and to answer the question within the educational curriculum of how many kanji characters need to be learned per day in order to learn all kanji characters. The goal is to create a more effective kanji learning curriculum.

## Necessary Domain Knowledge
To create a mathematical model for learning kanji characters, it is necessary to use data from a Japanese language course that teaches kanji characters. This data was obtained from Thammasat University and includes the following:
* Japanese 1: Students will learn a total of 80 kanji characters. No prerequisites.

* Japanese 2: Students will learn a total of 120 kanji characters. Prerequisite: Japanese 1.

* Japanese 3: Students will learn a total of 250 kanji characters. Prerequisite: Japanese 2.

* Japanese 4: Students will learn a total of 250 kanji characters. Prerequisite: Japanese 3.

* Japanese 5: Students will learn a total of 300 kanji characters. Prerequisite: Japanese 4.

* Japanese 6: Students will learn a total of 350 kanji characters. Prerequisite: Japanese 5.

* Additional Kanji: Students are required to learn an additional 786 kanji characters that are not included in Japanese 1 to Japanese 6. These characters can be studied independently.

## Symbols and Definitions
Symbol | Type | Variable | Unit
| :---: | :---: | :--- | :---:
$L(t)$  | Output variable | Number of kanji characters the learner knows at time t | Characters
$L_i(t)$  | Parameter | Number of kanji characters the learner knows during the learning period of Japanese i at time t | Characters
$K_i(t)$  | Parameter | Number of kanji characters the learner knows during the learning period of Japanese i at time t | Characters
$t(t)$  | Input variable | Time spent learning kanji characters | Days
$J_i$  | Parameter | Total number of kanji characters that can be learned during the learning period of Japanese i | Characters
$K_{0,i}$  | Parameter | Number of kanji characters that the learner already knows and remembers in Japanese i | Characters
$β$  | Parameter | Kanji character loss rate | Unitless

Where $L_i, K_i, J_i, K_{0,i}$ denoted by $i = 1,2,3,4,5,6$

## Kanji Learning Model
Let $K_i , K_{0,i} , t \in \mathbb{N} , \alpha , \beta \in \mathbb{R}^+$. <br>
This model defines $L(t)$, the number of kanji characters a learner knows at time t, as the sum of six components, $L_1(t),L_2(t),...,L_6(t)$ each representing learning during a specific time period:
$$L(t) = L_1(t) + L_2(t) + L_3(t) + L_4(t) + L_5(t) + L_6(t)$$
Where
$$L_1(t) = \min(J_1 + K_1, \left\lfloor (1 - \beta)(K_{0,1} + \alpha{t}) \right\rfloor) ; t \in (0,120]$$
$$L_2(t) = \min(J_2 + K_2, \left\lfloor (1 - \beta)(K_{0,2} + \alpha{(t - 120)}) \right\rfloor\)  ; t \in (120,240]$$
$$L_3(t) = \min(J_3 + K_3, \left\lfloor (1 - \beta)(K_{0,3} + \alpha{(t - 240)}) \right\rfloor\)  ; t \in (240,360]$$
$$L_4(t) = \min(J_4 + K_4, \left\lfloor (1 - \beta)(K_{0,4} + \alpha{(t - 360)}) \right\rfloor\)  ; t \in (360,480]$$
$$L_5(t) = \min(J_5 + K_5, \left\lfloor (1 - \beta)(K_{0,5} + \alpha{(t - 480)}) \right\rfloor\)  ; t \in (480,600]$$
$$L_6(t) = \min(J_6 + K_6, \left\lfloor (1 - \beta)(K_{0,6} + \alpha{(t - 600)}) \right\rfloor\)  ; t \in (600,720]$$

## Project Advisor
I am grateful for the support of Dr.rer.nat Ratthaprom Promkam. You can access his GitHub contributions [HERE](https://github.com/epsilonxe):
