# Udacity Deep Reinforcement Learning Nanodegree

## Project 2: Continuous Control

### Introduction

The goal of this project is to use Deep Reinforcement Learning
to train an agent to control the arms in a variation of the
[Unity ML-Agents Reacher Environment](https://github.com/Unity-Technologies/ml-agents/blob/master/docs/Learning-Environment-Examples.md#reacher).
The environment features double-jointed arms
with goal locations circling around them.
The agent must learn to apply the correct torque values
on the joints so the arm will remain in the target location.

The specific environment used here was provided by [Udacity](https://www.udacity.com/)
as part of the [Deep Reinforcement Learning Nanodegree Program](https://www.udacity.com/course/deep-reinforcement-learning-nanodegree--nd893)
and is based on the [Unity ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents).

#### Rewards

The agent is rewarded **`+0.1`** when the arm is in the goal location, **`0`** otherwise.

The goal is to maximize the cumulative reward over an episode,
i.e. find the location as quickly as possible and follow
it, as it moves, as closely as possible.

#### Actions

The agent controls two pairs of **continuous action values**
representing the **torque applied to each joint**:
- for each of the two joints, the torque is expressed as two `floats` between `-1.0` and `1.0`.

### State

The agent perceives the environment through a state vector
with 33 dimensions.
The state information contains the position, rotation, velocity, and angular velocities
of the two arm Rigidbodies.

#### Benchmark goal

An agent will not be deemed sufficiently well-trained if it does not achieve
a score greater than or equal to `+30` (averaged over `100` episodes).

### Setup

To run this project, you first need to install the [Anaconda Distribution](https://www.anaconda.com/distribution/).

In the **Anaconda Prompt**,
create an environment for the project with the following command:
```shell script
conda create --name arm python=3.6
```

Activate the environment with the following command
(prefix it with `source` on Linux):
```shell script
activate arm
```

#### PyTorch

Follow the [instructions from the PyTorch official website](https://pytorch.org/)
to install a PyTorch version that matches both your operating system and
your CUDA installation (if you want to use the GPU acceleration).

#### Requirements

If you have not done it already, clone this project with the following command:
```shell script
git clone https://github.com/NadCAtarun/arm-controller.git
cd arm-controller
```

From the **root folder** of this project,
run the following command
to install the required packages:
```shell script
pip install -r requirements.txt
```

**Note**: PyTorch was purposely left out of `requirements.txt`
since the compatibility with your local CUDA is way too tricky to infer.
Just putting a random version in the requirements would most likely fail.
That said, the project will only work if PyTorch is properly installed in the
`arm` environment.

#### Jupyter Kernel

Create an IPython kernel (to use on Jupyter) for the `arm` environment
with the following command:
```shell script
python -m ipykernel install --user --name arm --display-name "arm"
```

#### Unity Environment

Download the Unity environment (supplied by Udacity)
matching your operating system:
- [Linux](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Linux.zip)
- [Windows 64-bit](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86_64.zip)
- [Windows 32-bit](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher_Windows_x86.zip)
- [Mac OSX](https://s3-us-west-1.amazonaws.com/udacity-drlnd/P2/Reacher/Reacher.app.zip)

Unzip it in root folder of the project.

### Usage instructions

From the root folder or one of its parent folders,
launch Jupyter Notebook with the following command:
```shell script
jupyter notebook
```

Open the `Report.ipynb` with the `arm` kernel
and run its cells to train your own agent.
