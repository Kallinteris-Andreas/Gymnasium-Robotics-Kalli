---
hide-toc: true
firstpage:
lastpage:
---

```{toctree}
:hidden:
:titlesonly:
:caption: Introduction
content/installation
content/multi-goal_api
```

```{toctree}
:hidden:
:caption: Environments
envs/fetch/index
envs/hand/index
envs/hand_touch/index
envs/MaMuJoCo/index
```

```{toctree}
:hidden:
:caption: Development
Github <https://github.com/Farama-Foundation/Gymnasium-Robotics>
```
# Gymnasium-Robotics is a collection of robotics simulation environments for Reinforcement Learning


```{figure} _static/videos/fetch/FetchPickAndPlace.gif
   :alt: Fetch Pick And Place
   :width: 500
   :height: 500
```

This library contains a collection of Reinforcement Learning robotic environments that use the [Gymansium](https://gymnasium.farama.org/) API. The environments run with the [MuJoCo](https://mujoco.org/) physics engine and the maintained [mujoco python bindings](https://mujoco.readthedocs.io/en/latest/python.html).

The creation and interaction with the robotic environments follow the Gymnasium interface:

```{code-block} python

import gymnasium as gym
env = gym.make("FetchPickAndPlace-v2", render_mode="human")
observation, info = env.reset(seed=42)
for _ in range(1000):
   action = policy(observation)  # User-defined policy function
   observation, reward, terminated, truncated, info = env.step(action)

   if terminated or truncated:
      observation, info = env.reset()
env.close()
```