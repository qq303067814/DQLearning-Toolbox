# 强化学习工具箱(DRLToolbox)

## 概述
该项目建立了一个集成深度强化学习训练、训练结果可视化、调参、模型版本管理等功能于一体的工具箱，提供小游戏对算法进行测试学习。该工具箱可以帮助大家了解深度强化学习的乐趣以及协助开发者的研究。

## 配置情况
* Python 3
* TensorFlow-gpu
* pygame
* OpenCV-Python
* PyQt5
* sys
* threading
* multiprocessing
* shelve
* os
* sqlite3
* socket
* pyperclip
* flask
* glob
* shutil
* numpy
* pandas
* time
* importlib

## 如何运行？
运行run_window.py可启动窗口
+ 启动界面

![启动界面](启动界面.png)

+ 主界面

![主界面](主界面.png)

+ 设置界面

  ![设置窗口](设置窗口.png)


### 其他功能详见项目大报告

## 什么是强化学习？
详见报告

## 最终表现
以贪吃蛇为例，经过超过500万次训练（超过48小时），一共完成36171局，每局分数如下图：

![picture2](picture2.png)

截取一个片段如下：

![贪吃蛇终板](贪吃蛇终板.gif)

跳跳人目前训练了500万次，一共完成3886局，每局存活帧数如下图

![picture](picture.png)


截取一个片段如下：

![跳跳人1](跳跳人1.gif)

我们对跳跳人的学习速度进行了估计，我们认为从1000局之后跳跳人的学习速度大致符合二次函数而非指数函数，具体结果如下图：

![picture3](picture3.png)


## Deep Q-Network Algorithm
```python
Initialize replay memory D to size N
Initialize action-value function Q with random weights
for episode = 1, M do
    Initialize state s_1
    for t = 1, T do
        With probability ϵ select random action a_t
        otherwise select a_t=max_a  Q(s_t,a; θ_i)
        Execute action a_t in emulator and observe r_t and s_(t+1)
        Store transition (s_t,a_t,r_t,s_(t+1)) in D
        Sample a minibatch of transitions (s_j,a_j,r_j,s_(j+1)) from D
        Set y_j:=
            r_j for terminal s_(j+1)
            r_j+γ*max_(a^' )  Q(s_(j+1),a'; θ_i) for non-terminal s_(j+1)
        Perform a gradient step on (y_j-Q(s_j,a_j; θ_i))^2 with respect to θ
    end for
end for
```

## 开发者
**中山大学岭南学院**梁智鹏、陈昊、张意伟，同时感谢**中山大学岭南学院**张宏斌副教授的悉心指导和**中山大学数学学院**付星宇的理论指导。

## 参考文献
[1] Mnih Volodymyr, Koray Kavukcuoglu, David Silver, Andrei A. Rusu, Joel Veness, Marc G. Bellemare, Alex Graves, Martin Riedmiller, Andreas K. Fidjeland, Georg Ostrovski, Stig Petersen, Charles Beattie, Amir Sadik, Ioannis Antonoglou, Helen King, Dharshan Kumaran, Daan Wierstra, Shane Legg, and Demis Hassabis. **Human-level Control through Deep Reinforcement Learning**. Nature, 529-33, 2015.

[2] Volodymyr Mnih, Koray Kavukcuoglu, David Silver, Alex Graves, Ioannis Antonoglou, Daan Wierstra, and Martin Riedmiller. **Playing Atari with Deep Reinforcement Learning**. NIPS, Deep Learning workshop

[3] Kevin Chen. **Deep Reinforcement Learning for Flappy Bird** [Report](http://cs229.stanford.edu/proj2015/362_report.pdf) | [Youtube result](https://youtu.be/9WKBzTUsPKc)

[4] Flood Sung. **Deep Reinforcement Learning 基础知识（DQN方面）**https://blog.csdn.net/songrotek/article/details/50580904

[5]Giannoccarro Ilaria and Peperpaolo Pontrandolfo. **Inventory management in supply chains: a reinforcement learning approach**, *International Journal of Production economics*, 2002, 153-161

[6] Zhengyao Jiang, Dixing Xu and Jinjun Liang. **A Deep Reinforcement Learning Framework for the Financial Portfolio Management Problem**,https://arxiv.org/abs/1706.10059
