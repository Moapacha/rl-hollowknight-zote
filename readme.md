# How to run

https://github.com/seermer/HollowKnight_RL  

The code is based on this repo, so if you want to run this program, you need to go to the original author's code repository and download the "Enemybloodbar" mod, change the game resolution and window mode, and then you also need to beat the Hollow Knight to the God's House and unlock zote.

Also, my keystrokes are move: a & d; up and down: w & s; attack: j; jump: k.

Run model.py to start training, and change the timed save step interval in callback2.

Runs in Python 3.9.

Using PPO as model.

model -> change callback -> continue -> test

# My changes

Rewriting env, the rest is written in stablebaseline3.

# Differences from the original author:

1. from 0.3s per step to 0.15s per step
2. the network is different, see model.py for details
3. ai can now choose how high to jump
4. use ppo instead of dqn, of course, under the framework of stablebaseline3, it is still convenient to change the algorithm
5. add downward slash
6. add dash and no attack
7. add zote to boss

# Known bugs:

1. the window mode of hollow knight is scalable, don't accidentally stretch or shrink it; and it is better not to enable the steam interface in the game, the blood bar may be covered by the friends' messages

# Future updates:

1. remove stay, since reducing the STEP interval makes moving left and right good enough for any action

2. add more information to the model inputs, sprint hardening, movement in the last few frames

3. improve the order of execution between jump, move, and dash, because if this frame is a dash, then jumping becomes pointless and a waste of jumps
