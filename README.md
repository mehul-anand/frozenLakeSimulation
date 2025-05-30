> NOTE : Under Development

## Contents
- [Frozen Lake Simulation](#frozen-lake-simulation)
  - [Environment](#environment)
    - [Description](#description)
    - [Objective](#objective)
    - [Agent Navigation](#agent-navigation)
  - [Training](#training)
  - [Testing](#testing)
  - [**Output Summary**](#output-summary)
  - [**Final Q-table**](#final-q-table)
  - [**Evaluation Episodes**](#evaluation-episodes)
    - [**Episode Format**](#episode-format)
    - [**Episodes 1 to 20**](#episodes-1-to-20)
  - [Sources](#sources)

# Frozen Lake Simulation

## Environment

<p align="center">
    <img src="./content/images/environment.png" alt="environment"/>
</p>

### Description
> | Component           | Visual                                                                | Description                                                                                                                  |
> | ------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
> | **Agent (Elf)**     | ELf                                                                   | The agent (an elf character here) learns to navigate from the start to the goal by maximizing cumulative reward.             |
> | **Start Tile**      | Brown square                                                          | The agent’s starting position (top-left corner, typically state 0).                                                          |
> | **Frozen Tiles**    | White/blue icy tiles                                                  | Safe tiles that the agent can walk on. These are non-terminal, neutral reward states.                                        |
> | **Holes (Hazards)** | Blue water pits                                                       | Dangerous tiles—falling in results in the episode ending with a **reward of 0**. The agent must learn to avoid these.        |
> | **Goal (Gift Box)** | Present icon                                                          | The goal state, often located at the bottom-right. Reaching this yields a **reward of 1** and ends the episode successfully. |

### Objective
> The goal of the Frozen Lake simulation is for the agent to find the optimal path from the start tile to the goal, avoiding the holes.  
> The agent uses a policy learned via reinforcement learning , which maps each state to the best action.

### Agent Navigation 
<p align="center">
    <img src="https://gymnasium.farama.org/_images/frozen_lake.gif" alt="Frozen Lake Animation"/>
</p>

- agent navigates the path via a Q-learning algorithm

- the agent explores and then exploits it's environment

## Training
<div>
    <a href="https://www.loom.com/share/85a833789a63478ab540263b67eedd10">
      <p>Frozen Lake Training - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/85a833789a63478ab540263b67eedd10">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/85a833789a63478ab540263b67eedd10-772b51c09255813f-full-play.gif">
    </a>
</div>

## Testing
<div>
    <a href="https://www.loom.com/share/6c5295e3274e49de94ca434a388e6ffb">
      <p>Frozen Lake Working - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/6c5295e3274e49de94ca434a388e6ffb">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/6c5295e3274e49de94ca434a388e6ffb-1ed4a7864ffee63f-full-play.gif">
    </a>
</div>

## **Output Summary**

> | Metric                      | Value                            |
> |----------------------------|----------------------------------|
> | **Training Status**        | Completed                        |
> | **Success Rate**           | 0.875 (8750 successful episodes) |
> | **Average Reward**         | 0.875                            |

---

## **Final Q-table**

> | State | Action 0     | Action 1     | Action 2     | Action 3     |
> |-------|--------------|--------------|--------------|--------------|
> | 0     | 0.94148015   | 0.95099005   | 0.95099005   | 0.94148015   |
> | 1     | 0.94148015   | 0.00000000   | 0.96059601   | 0.95099005   |
> | 2     | 0.95099005   | 0.97029900   | 0.95099005   | 0.96059601   |
> | 3     | 0.96059601   | 0.00000000   | 0.95098727   | 0.95098986   |
> | 4     | 0.95099005   | 0.96059601   | 0.00000000   | 0.94148015   |
> | 5     | 0.00000000   | 0.00000000   | 0.00000000   | 0.00000000   |
> | 6     | 0.00000000   | 0.98010000   | 0.00000000   | 0.96059601   |
> | 7     | 0.00000000   | 0.00000000   | 0.00000000   | 0.00000000   |
> | 8     | 0.96059601   | 0.00000000   | 0.97029900   | 0.95099005   |
> | 9     | 0.96059601   | 0.98010000   | 0.98010000   | 0.00000000   |
> | 10    | 0.97029900   | 0.99000000   | 0.00000000   | 0.97029900   |
> | 11    | 0.00000000   | 0.00000000   | 0.00000000   | 0.00000000   |
> | 12    | 0.00000000   | 0.00000000   | 0.00000000   | 0.00000000   |
> | 13    | 0.00000000   | 0.98010000   | 0.99000000   | 0.97029900   |
> | 14    | 0.98010000   | 0.99000000   | 1.00000000   | 0.98010000   |
> | 15    | 0.00000000   | 0.00000000   | 0.00000000   | 0.00000000   |

---

## **Evaluation Episodes**

Each episode follows a successful 6-step path from Start to Goal.

---

### **Episode Format**

> | Step | State | Action | New State | Reward |
> |------|-------|--------|-----------|--------|
> | 0    | 0     | 1      | 4         | 0.0    |
> | 1    | 4     | 1      | 8         | 0.0    |
> | 2    | 8     | 2      | 9         | 0.0    |
> | 3    | 9     | 1      | 13        | 0.0    |
> | 4    | 13    | 2      | 14        | 0.0    |
> | 5    | 14    | 2      | 15        | 1.0    |

**Total Steps:** 6  
**Final Reward:** 1.0

---

### **Episodes 1 to 20**

All 20 evaluation episodes follow the same trajectory:

> | Episode | Steps Taken | Final Reward |
> |---------|-------------|---------------|
> | 1       | 6           | 1.0           |
> | 2       | 6           | 1.0           |
> | 3       | 6           | 1.0           |
> | 4       | 6           | 1.0           |
> | 5       | 6           | 1.0           |
> | 6       | 6           | 1.0           |
> | 7       | 6           | 1.0           |
> | 8       | 6           | 1.0           |
> | 9       | 6           | 1.0           |
> | 10      | 6           | 1.0           |
> | 11      | 6           | 1.0           |
> | 12      | 6           | 1.0           |
> | 13      | 6           | 1.0           |
> | 14      | 6           | 1.0           |
> | 15      | 6           | 1.0           |
> | 16      | 6           | 1.0           |
> | 17      | 6           | 1.0           |
> | 18      | 6           | 1.0           |
> | 19      | 6           | 1.0           |
> | 20      | 6           | 1.0           |

## Sources
> [Farama Org's Page for frozen lake setup](https://gymnasium.farama.org/environments/toy_text/frozen_lake/)  
>
> [Gymnasium's paper on arxiv](https://arxiv.org/abs/2407.17032#)
>
> [Q-Learning via the cricket example - notion notes](https://mehulanand.notion.site/Q-Learning-1ee6fa2f12cc8092884dd23346f99933?pvs=4)
>
> [Exploration v/s Exploitation via the cricket example - notion notes](https://mehulanand.notion.site/Exploration-vs-Exploitation-1f46fa2f12cc80278edfe221b6786e5a?pvs=4)