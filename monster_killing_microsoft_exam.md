[http://hihocoder.com/problemset/problem/1491](http://hihocoder.com/problemset/problem/1491)

需要登录（微博登录）

---
时间限制:10000ms
单点时限:1000ms
内存限制:256MB
描述
In a video game Little Hi is trapped in a maze. The maze can be considered as an N × M grid. There are monsters on some cells. Each cell has one monster at most. Below is an example of a 4x5 maze. '.' represents an empty cell. 'D' represents the entrance, Little Hi's starting point. 'M' represents a normal monster. 'S' represents a special monster.  

..S..
M...M
..D..
.M...
At the beginning, each cell is covered by a slate except that the slate on the entrance cell has been already removed. Each round Little Hi may either remove a slate as long as

1. each monster has either been killed or still covered by a slate, and

2. the cell covered by the slate is adjacent to some cell whose slate has been already removed. (Two cells are adjacent if they share a common side.)

or attack a monster as long as the slate covering it has been removed.

At the beginning Little Hi has Hp hit points and Ap attack points. Each monster also has its hit points Hi and attack points Ai. When Little Hi attacks a monster, the hit points of both sides should subtract the attack points of the other side.

For example, if Little Hi's hit points are 50 and attack points are 30. When he attacks a monster whose hit points are 25 and attack points are 10, the remaining hit points for Little Hi are 40 and the remaining hit points for the monster are -5.

When hit points are less than or equal to 0 the monster is killed.

At the beginning Little Hi has a buff called "Destruction Blade" which lasts for 5 rounds. With such buff Little Hi does not take damage when he attacks a monster. The buff vanishes after 5 rounds but can be refreshed or regained for the following 5 rounds after killing a special monster. (Note that the buff always lasts for 5 rounds after killing a special monster no matter how many rounds left before killing the monster.)

Now given the map of the maze. Can you tell whether Little Hi can kill all the monsters? If he can what is the maximum remaining hit points?

输入
Line 1: two integers N and M. (2 ≤ N, M ≤ 6, N × M ≤ 20)

Line 2 .. N+1: M characters per line, representing the maze map.

Line N+2 .. N+K+1: two integers Hi and Ai per line, representing the hit points and attack points for each monster, from top to bottom and left to right. (3 ≤ K ≤ 7)

Line N+K+2: two integers Hp and Ap, the hit points and attack points for Little Hi.

输出
If Little Hi can kill all the monsters and stay alive output the maximum remaining hit points. Otherwise output DEAD.

样例解释
Let's assume the upper left cell is (1, 1).

Round 1: remove slate (2, 3), buff remains 4 rounds

Round 2: remove slate (2, 2), buff remains 3 rounds

Round 3: remove slate (2, 1), buff remains 2 rounds

Round 4: attack monster (2, 1), take no damage, buff remains 1 round

Round 5: attack monster (2, 1), take no damage, monster killed, buff vanishes

Round 6: remove slate (2, 4)  

Round 7: remove slate (4, 3)  

Round 8: remove slate (1, 3)  

Round 9: attack monster (1, 3), take 5 damage, HP=55

Round 10: attack monster (1, 3), take 5 damage, HP=50, monster killed, buff remains 5 rounds

Round 11: remove slate (2, 5), buff remains 4 rounds

Round 12: attack monster (2, 5) take no damage, buff remains 3 rounds

Round 13: attack monster (2, 5) take no damage, buff remains 2 rounds

Round 14: remove slate (4, 2), buff remains 1 round

Round 15: attack monster (4, 2), take no damage, buff vanishes

Round 16: attack monster (4, 2), take 5 damage, HP=45, monster killed

样例输入
4 5  
..S..  
M...M  
..D..  
.M...  
20 5  
20 5  
20 5  
20 5  
60 10
样例输出
45

----
描述
在一个视频游戏中，Little Hi被困在一个迷宫中。迷宫可以被认为是N × M网格。某些单元格上有怪物。每个单元格最多只有一个怪物。以下是4x5迷宫的示例。'.' 代表一个空单元格。'D'代表入口，Little Hi的起点。'M'代表一个普通的怪物。'S'代表一个特殊的怪物。  

..S ..
M...M
..D ..
.M ...
开始时，每个单元都被板岩覆盖，除了入口单元上的板岩已经被移除。每一轮Little Hi都可以删除一块石板

1.每个怪物要么被杀死，要么仍被石板覆盖

2.板岩覆盖的单元格与某些板岩已经被移除的单元格相邻。

只要覆盖怪物的石板被移除，就攻击怪物。

一开始Little Hi有Hp生命值和Ap攻击点。每个怪物也有其生命值H i和攻击点A i。当Little Hi攻击怪物时，双方的生命值应该减去对方的攻击点。

例如，如果Little Hi的生命值为50，攻击点数为30.当他攻击一个生命值为25且攻击点数为10的怪物时，Little Hi的剩余生命值为40，怪物的剩余生命值为-5。

当生命值小于或等于0时，怪物将被杀死。

起初，Little Hi有一个名为“Destruction Blade”的buff（盾牌），持续5轮。有了这样的buff，Little Hi在攻击怪物时不会受到伤害。buff在5轮后消失，但在杀死一个特殊怪物后可以在接下来的5轮中恢复。（注意，在杀死一个特殊怪物之后，无论在杀死怪物之前剩下多少轮，buff都会持续5轮。）

现在给出了迷宫的地图。你能说出Little Hi是否可以杀死所有的怪物？如果可以，他可以获得最大剩余生命值？

输入
第1行：两个整数N和M。(2 ≤ N, M ≤ 6, N × M ≤ 20)

第2行到N +1行：每行M个字符，代表迷宫地图。

N +2 .. N + K +1：每行两个整数H i和A i，表示每个怪物的生命值和攻击点，从上到下，从左到右。（3≤ K ≤7）K个怪物

N + K +2：两个整数Hp和Ap，Little Hi的生命值和攻击点。

输出
如果Little Hi可以杀死所有怪物并保持活着输出剩余的最大生命值。否则输出DEAD。

样例解释
我们假设左上角的单元格是（1,1）。
..S ..
M...M
..D ..
.M ...
第1轮：移除板岩（2,3），buff保持4轮

第2轮：移除板岩（2,2），buff保持3轮

第3轮：移除板岩（2,1），buff保持2轮

第4轮：攻击怪物（2,1），不受伤害，buff保持1轮（趁盾牌还在攻击怪物）

第5轮：攻击怪物（2,1），不受伤害，怪物死亡，buff消失

第6轮：删除石板（2,4）  ---无敌之后，方便攻击（2，5）的怪物

第7轮：删除石板（4,3）  ---无敌之后，方便攻击（4，2）的怪物

第8轮：删除石板（1,3）  

第9轮：攻击怪物（1,3），受到5点伤害，HP = 55 （先攻击特殊怪物）

第10轮：攻击怪物（1,3），受到5点伤害，HP = 50，怪物死亡，buff仍然是5轮

第11轮：移除板岩（2,5），buff保持4轮

第12轮：攻击怪物（2,5）不受伤害，buff仍然是3轮

第13轮：攻击怪物（2,5）不受伤害，buff仍然是2轮

第14轮：移除板岩（4,2），buff保持1轮

第15轮：攻击怪物（4,2），不受伤害，buff消失

第16轮：攻击怪物（4,2），受到5点伤害，HP = 45，怪物死亡

样例输入
4 5  
..S..  
M...M  
..D..  
.M...  
20 5  
20 5  
20 5
20 5  
60 10
样例输出
45

---

###解题思路
在初始状态下：

1.入口相邻的石板（可能有多种情况）揭开（可能需要打怪物），耗费的血量needHP；
2.入口相邻的石板（可能有多种情况）揭开后（相当于减少了一个单元格），这些种情况中，耗费血量的最小值是多少minHP（保存在二维状态数组dp[buff][state]中）

dp[buff][state] = Math.min(HP, needHP + minHP);
//这里dp[i][j]代表的是，剩余i个buffer，在j状态（计算出来的int值），最少需要多少hp才能杀死所有monster。

//总的状态有2^20*6种。
//其中2^20是矩阵最多有的状态，
//6是有buffer0~5六种状态。
//对于矩阵（最大有20格子），每个格子有两种选择：揭开了还是没有揭开。
//所以我们可以将揭开的格子设置为‘D’，然后计算目前格子对应的状态值是多少，
```
        for (int i = 0; i < mazeMap.length; i++) {
            for (int j = 0; j < mazeMap[i].length; j++) {
                state <<= 1;//每个格子有两种选择：石板揭开了还是没有揭开。
                if (mazeMap[i][j] != 'D') {
                    state += 1;//石板揭开了
                }
            }
        }
```
//最后结果就是HP-dp[5][initstate]。
大于0就是结果，小于等于0输出dead

dp状态二维数组简图如下：

![image.png](https://upload-images.jianshu.io/upload_images/468490-35c0ca249fe7ea39.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

```
package com.company;

import java.util.*;


class Monster {
    String ij;
    int hp;
    int ap;

    Monster(String ij, int hp, int ap) {
        this.ij = ij;
        this.hp = hp;
        this.ap = ap;
    }
}

//总的状态有2^20*6种。
//其中2^20是矩阵最多有的状态，
//6是有buffer0~5六种状态。
//对于矩阵（最大有20格子），每个格子有两种选择：揭开了还是没有揭开。
//所以我们可以将揭开的格子设置为‘D’，然后计算目前格子对应的状态值是多少，
//这里dp[i][j]代表的是，剩余i个buffer，在j状态（计算出来的int值），最少需要多少hp才能杀死所有monster。
//最后结果就是HP-dp[5][initstate]。
public class Main {
    private static final int MAX_STATE = (1 << 20), ROUND = 5;
    static int N, M, HP, AP;
    static int[][] dp = new int[ROUND + 1][MAX_STATE];
    static Map<String, Monster> monsterMap = new HashMap<>();


    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        N = scanner.nextInt();
        M = scanner.nextInt();
        char[][] mazeMap = new char[N][M];
        List<String> monsterIndex = new ArrayList<>();//怪物在迷宫中的坐标列表
        scanner.nextLine();
        //读取迷宫信息，保存到二维数组mazeMap，并用monsterIndex保存怪物在迷宫中的坐标列表
        for (int i = 0; i < N; i++) {
            String line = scanner.nextLine();
            line = line.trim();
            mazeMap[i] = line.toCharArray();//指向（保存）本行字符集合
            for (int j = 0; j < M; j++) {
                if (mazeMap[i][j] == 'S' || mazeMap[i][j] == 'M')
                    monsterIndex.add(i + "" + j);
            }
        }
        //遍历怪物坐标列表，创建怪物对象，保存到怪物map
        for (int pos = 0; pos < monsterIndex.size(); pos++) {
            int hp, ap;
            hp = scanner.nextInt();
            ap = scanner.nextInt();
            String index = monsterIndex.get(pos);
            Monster monster = new Monster(index, hp, ap);
            monsterMap.put(index, monster);
        }

        HP = scanner.nextInt();//小Hi血量
        AP = scanner.nextInt();//小Hi攻击力

        //状态二维数组，初始化为最大值
        for (int i = 0; i <= ROUND; i++) {
            for (int j = 0; j < MAX_STATE; j++) {
                dp[i][j] = Integer.MAX_VALUE;
            }
        }

        int remainHp = HP - letKill(mazeMap, ROUND);

        if (remainHp <= 0)
            System.out.println("DEAD");
        else
            System.out.println(remainHp);
    }

    static int letKill(char[][] mazeMap, int buff) {

        int state = 0, remainMonster = 0;
        Set<String> candidates = new HashSet<>();//候选攻击集合

        for (int i = 0; i < mazeMap.length; i++) {
            for (int j = 0; j < mazeMap[i].length; j++) {
                state <<= 1;//每个格子有两种选择：石板揭开了还是没有揭开。
                if (mazeMap[i][j] != 'D') {
                    state += 1;//石板揭开了
                    if (mazeMap[i][j] != '.')
                        remainMonster++;
                    if (i - 1 >= 0 && mazeMap[i - 1][j] == 'D' //不是第一行，并且上边的石板已经被揭开
                            || j - 1 >= 0 && mazeMap[i][j - 1] == 'D'//不是第一列，并且左边的石板已经被揭开
                            || i + 1 < N && mazeMap[i + 1][j] == 'D'//不是最后一行，并且下边的石板已经被揭开
                            || j + 1 < M && mazeMap[i][j + 1] == 'D'//不是最后一列，并且右边的石板已经被揭开
                            )
                        candidates.add(i + "" + j);
                }
            }
        }
        //边界
        // state == 0 意味着石板全部被揭开
        if (remainMonster == 0 || state == 0)
            return 0;//不需要费血

        //别的路径算出来的此状态下的耗血值
        if (dp[buff][state] != Integer.MAX_VALUE)
            return dp[buff][state];

        dp[buff][state] = HP;//英雄血量的最大值
        //所有候选，挨个试探
        for (String candidate : candidates) {
            int i = candidate.charAt(0) - '0', j = candidate.charAt(1) - '0';
            char curChar = mazeMap[i][j];
            int curBuff = buff - 1, needHP = 0;
            if (mazeMap[i][j] == 'M' || mazeMap[i][j] == 'S') {//attack
                Monster monster = monsterMap.get(i + "" + j);
                int monsterHP = monster.hp;
                while (monsterHP > 0) {
                    monsterHP -= AP;
                    if (curBuff <= 0)
                        needHP += monster.ap;
                    curBuff--;
                }
            }
            if (needHP >= HP)//英雄死了，不是很好的候选
                continue;
            
            if (mazeMap[i][j] == 'S')
                curBuff = ROUND;
            else
                curBuff = curBuff <= 0 ? 0 : curBuff;
            
            mazeMap[i][j] = 'D';//石板掀开（怪物杀死也被看作石板掀开）
            
            int minHP = letKill(mazeMap, curBuff);//探索又有一块石板被掀开后的新迷宫
            
            mazeMap[i][j] = curChar;//恢复单元格的原来样子
            
            if (minHP >= HP)//英雄死了，不是很好的候选
                continue;
            
            dp[buff][state] = Math.min(dp[buff][state], needHP + minHP);
        }
        return dp[buff][state];
    }
}


```
