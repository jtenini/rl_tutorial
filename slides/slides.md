---
theme: gaia
class: lead
paginate: true
backgroundColor: #fff
backgroundImage: url('https://marp.app/assets/hero-background.svg')
---

# **RL in Application**

When and how RL approaches can add value in your applications.

https://github.com/jtenini/rl_tutorial

Joe Tenini, PhD
Principal Data Scientist - Red Ventures
Applied Machine Learning - DSBA - UNC Charlotte

---

# Agenda

- Why you should care.
- How it works.
- How you should invest.

---

# Why should I care about RL?

- Exciting RL Trophies :trophy: and examples :octopus:
- Comprehensive framework for decision making
- Untapped potential (tooling not commoditized) :robot:

---

# Exciting trophies :trophy:

- [Playing Atari with Deep Reinforcement Learning](https://www.deepmind.com/publications/playing-atari-with-deep-reinforcement-learning) :space_invader:
	- 2013, Deepmind: Mnih, Kavukcuoglu, Silver et al
	- Deep Q-Learning
- State: Pixel values.
- Action: Next button push.
- Reward: Point change.

---

# Exciting trophies :trophy:

- [Mastering the game of Go with deep neural networks and tree search](https://www.nature.com/articles/nature16961) :black_circle: :white_circle:
	- 2016, Deepmind: Silver et al
	- Monte Carlo Tree Search
	- Defeats 18x world champion Lee Sedol
- State: Board position.
- Action: Placing a stone.
- Reward: 1 if winning move, else 0.

---

# Exciting trophies :trophy:

- [OpenAI Five plaing Dota 2](https://openai.com/five/) :mage:
	- 2019, OpenAI, Berner et al
	- 10,000 years of gameplay (10 months of real training).
	- Proximal Policy Optimization
	- Defeats world champion _team_ OG.
- State: Partial state observation.
- Action: Mouse and button input.
- Rewards: Shaped rewards.

---

# Exciting trophies :trophy:

Common threads: 
1. As much data as you want (self-play).
2. (Semi)-deterministic environments.

---

# Exciting trophies :trophy:

Common threads: 
1. As much data as you want (self-play).
2. (Semi)-deterministic environments.

Can we still be successful without these?

---

# Examples of RL in practical business application:

Useful simplification 1:

[Bandit problems](https://arxiv.org/search/?query=bandit&searchtype=all&source=header&start=0) (epsiode length 1)

---

# What is the bandit problem?

This happens over and over:
1. You recieve a state $x \in \mathbb{R}^n$ sampled from an unknown static distribution $P(x)$.
2. You choose an action $a \in A$ from a finite set.
3. You recieve a real reward $r \in \mathbb{R}$ sampled from an unknown static distribution $P(r | x, a)$.

Goal: Maximize $\sum r$.

---

# What is the bandit problem?

This happens over and over:
1. You recieve a user represented by $x \in \mathbb{R}^n$.
2. You choose an experience or offer $a \in A$ from a finite set.
3. The user transacts (or doesn't) resulting in revenue $r \in \mathbb{R}$.

Goal: Maximize $\sum r$.

---

# Demo 1 - bandits

---

# Can we do better than epsilon greedy?

Practical advice:
1. It will depend on your environment.
2. For most environments, it's particularly difficult.
3. Often you'll introduce additional parameters that are hard to tune in practice.

---

# Can we do better than epsilon greedy?

[SquareCB](https://arxiv.org/pdf/2002.04926.pdf) is a nice option:

- Instead of choosing each option with probability $1/k\epsilon \dots$
- Choose each option with probability 
$$\frac{1}{\mu - \gamma (q(x,a^*)-q(x,a))}$$

---
