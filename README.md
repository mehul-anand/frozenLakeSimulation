> NOTE : This project is under development

## Contents
- [**Frozen Lake Simulation**](#frozen-lake-simulation)
  - [**Environment**](#environment)
    - [**Description**](#description)
    - [**Objective**](#objective)
    - [**Agent Navigation**](#agent-navigation)
- [**Deterministic system**](#deterministic-system)
  - [**Training (det)**](#training-det)
  - [**Testing (det)**](#testing-det)
  - [**Output Summary (det)**](#output-summary-det)
  - [**Final Q-table (det)**](#final-q-table-det)
- [**Non Deterministic system**](#non-deterministic-system)
  - [**Training (non det)**](#training-non-det)
  - [**Testing (non det)**](#testing-non-det)
  - [**Output Summary ( non det)**](#output-summary--non-det)
  - [**Final Q-table (non det)**](#final-q-table-non-det)
  - [**Sources**](#sources)

# **Frozen Lake Simulation**

## **Environment**

<p align="center">
    <img src="./content/images/environment.png" alt="environment"/>
</p>

### **Description**
> | Component           | Visual                                                                | Description                                                                                                                  |
> | ------------------- | --------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- |
> | **Agent (Elf)**     | ELf                                                                   | The agent (an elf character here) learns to navigate from the start to the goal by maximizing cumulative reward.             |
> | **Start Tile**      | Brown square                                                          | The agent’s starting position (top-left corner, typically state 0).                                                          |
> | **Frozen Tiles**    | White/blue icy tiles                                                  | Safe tiles that the agent can walk on. These are non-terminal, neutral reward states.                                        |
> | **Holes (Hazards)** | Blue water pits                                                       | Dangerous tiles—falling in results in the episode ending with a **reward of 0**. The agent must learn to avoid these.        |
> | **Goal (Gift Box)** | Present icon                                                          | The goal state, often located at the bottom-right. Reaching this yields a **reward of 1** and ends the episode successfully. |

### **Objective**
> The goal of the Frozen Lake simulation is for the agent to find the optimal path from the start tile to the goal, avoiding the holes.  
> The agent uses a policy learned via reinforcement learning , which maps each state to the best action.

### **Agent Navigation**
<p align="center">
    <img src="https://gymnasium.farama.org/_images/frozen_lake.gif" alt="Frozen Lake Animation"/>
</p>

- agent navigates the path via a Q-learning algorithm

- the agent explores and then exploits it's environment

# **Deterministic system**
> `is_slippery=False`
> - removes friction
## **Training (det)**
<div>
    <a href="https://www.loom.com/share/85a833789a63478ab540263b67eedd10">
      <p>Frozen Lake Training - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/85a833789a63478ab540263b67eedd10">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/85a833789a63478ab540263b67eedd10-772b51c09255813f-full-play.gif">
    </a>
</div>

## **Testing (det)**
<div>
    <a href="https://www.loom.com/share/6c5295e3274e49de94ca434a388e6ffb">
      <p>Frozen Lake Working - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/6c5295e3274e49de94ca434a388e6ffb">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/6c5295e3274e49de94ca434a388e6ffb-1ed4a7864ffee63f-full-play.gif">
    </a>
</div>

## **Output Summary (det)**

> | Metric                      | Value                            |
> |----------------------------|----------------------------------|
> | **Training Status**        | Completed                        |
> | **Success Rate**           | 0.875 (8750 successful episodes) |
> | **Average Reward**         | 0.875                            |

---

## **Final Q-table (det)**

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

# **Non Deterministic system**
> `is_slippery=True`
> - considers friction

## **Training (non det)**
<div>
    <a href="https://www.loom.com/share/5f48877d467848faa250507e95cc0580">
      <p>Frozen Lake Training UC - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/5f48877d467848faa250507e95cc0580">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/5f48877d467848faa250507e95cc0580-f0f07f02d7cd174c-full-play.gif">
    </a>
  </div>

## **Testing (non det)**
<div>
    <a href="https://www.loom.com/share/15c5d2d687194577abae7e122d53f8eb">
      <p>Frozen Lake Working UC - Watch Video</p>
    </a>
    <a href="https://www.loom.com/share/15c5d2d687194577abae7e122d53f8eb">
      <img style="max-width:300px;" src="https://cdn.loom.com/sessions/thumbnails/15c5d2d687194577abae7e122d53f8eb-a0bffbd8489f64f9-full-play.gif">
    </a>
  </div>

## **Output Summary ( non det)**

> | Metric                      | Value                            |
> |----------------------------|----------------------------------|
> | **Training Status**        | Completed                        |
> | **Success Rate**           | 0.647 (45,324 successful episodes) |
> | **Average Reward**         | 0.020                            |

---

## **Final Q-table (non det)**

> ### **Q-table (Non-Deterministic Frozen Lake)**
>
>| State | Action 0     | Action 1     | Action 2     | Action 3     |
>|-------|--------------|--------------|--------------|--------------|
>| 0     |  0.0584      | -0.0636      | -0.0519      | -0.0639      |
>| 1     | -0.5997      | -0.2800      | -0.4204      | -0.0139      |
>| 2     | -0.1675      | -0.1848      | -0.1937      | -0.0615      |
>| 3     | -0.2308      | -0.5553      | -0.2806      | -0.0802      |
>| 4     |  0.1150      | -0.2949      | -0.5490      | -0.4574      |
>| 5     |  0.0000      |  0.0000      |  0.0000      |  0.0000      |
>| 6     | -0.0529      | -0.6393      | -0.6621      | -0.7266      |
>| 7     |  0.0000      |  0.0000      |  0.0000      |  0.0000      |
>| 8     | -0.1037      | -0.2630      | -0.1112      |  0.2657      |
>| 9     | -0.2463      |  0.4770      | -0.0857      | -0.0848      |
>| 10    |  0.4170      | -0.2305      | -0.2821      | -0.6347      |
>| 11    |  0.0000      |  0.0000      |  0.0000      |  0.0000      |
>| 12    |  0.0000      |  0.0000      |  0.0000      |  0.0000      |
>| 13    |  0.0182      | -0.0374      |  0.6709      |  0.0517      |
>| 14    |  0.3709      |  0.8636      |  0.3932      |  0.4078      |
>| 15    |  0.0000      |  0.0000      |  0.0000      |  0.0000      |

---

> My notes
> - accuracy can be improved on the UC method
> - different Q-Learning methods can be explored


---


## **Sources**
> [Farama Org's Page for frozen lake setup](https://gymnasium.farama.org/environments/toy_text/frozen_lake/)  
>
> [Gymnasium's paper on arxiv](https://arxiv.org/abs/2407.17032#)
>
> [Q-Learning via the cricket example - notion notes](https://mehulanand.notion.site/Q-Learning-1ee6fa2f12cc8092884dd23346f99933?pvs=4)
>
> [Exploration v/s Exploitation via the cricket example - notion notes](https://mehulanand.notion.site/Exploration-vs-Exploitation-1f46fa2f12cc80278edfe221b6786e5a?pvs=4)