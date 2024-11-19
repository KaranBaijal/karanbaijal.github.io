---
layout: page
title: "AdaTAMP"
description: Multi-collaborative Task and Motion Planning with Feedback Loop using Embodied LLM Agents
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---
## Objective
Develop a multi-agent, collaborative framework for task and motion planning of human agents with a self-feedback loop using the VirtualHome Simulator. We aim to 

## Introduction and Related Work
Autonomous agents capable of performing tasks accurately while being able to perceive and respond in a dynamic environment has been an important goal in artificial intelligence (AI). Sequential long-horizon planning for embodied agents requires not only reasoning and formulating a series of dependent actions over extended time scales, but also ensuring the feasibility of executing these actions under environment and physical constraints. Task and Motion Planning (TAMP) is a methodological framework that hierarchically divides planning into two stages: high-level symbolic planning to reason over abstract action sequences and low-level continuous motion planning to compute feasible trajectories subject to physical constraints . Classical solutions like the Planning Domain Definition Language (PDDL) typically use specific modules to interface symbolic and continuous representations by generating real-valued parameters for symbolic actions and providing numerical goals to the motion planner. However, these approaches often require manual domain-specific design and struggle with long-horizon task planning and real-time adaptability, limiting generalization in dynamic environments.

Recent advancements in Large Language Models (LLMs), such as GPT-4, have demonstrated capabilities in reasoning, problem-solving, and embodied task planning. LLMs have shown the ability to serve as task planners by decomposing long-horizon tasks into a sequence of sub-tasks based on natural language instructions. For instance, Huang et al. translates high-level plans (e.g., “make breakfast”) into mid-level actionable steps (e.g., “open fridge”) using language models. Some researchers have also proposed iterative self-refinement strategies that refine initial plans through environmental feedback to improve complex sequential decision-making where each mid-level action influences subsequent ones. While LLMs perform reasonably well at high-level planning, they often struggle to translate these plans into precise low-level actions (i.e., motion control) and account for real-world constraints and dynamic environments, which must be optimized together for many embodied tasks. Many existing methods do not effectively explore the integration of continuous motion planning necessary for handling complex embodied environments, and lack a robust mechanism for real-time self-correction based on motion execution feedback. Additionally, the above methods mainly focus on robot manipulation rather than determining optimal paths for navigating to and completing a long-horizon task ina  dynamic environment with multiple agents and objects.

To address these limitations, we present AdaTAMP, an LLM-based adaptive TAMP framework that combines continuous motion planning with a self-feedback loop for real-time correction to enhance the integration of symbolic task planning and motion execution for embodied agents in household environments. Our contribution can be summarized as follows:

    1. We present the AdaTAMP framework, which integrates symbolic task sequences with continuous motion planning to improve task execution for embodied agents in a multi-agent setting.
    2. We incorporate a self-feedback loop that allows for real-time corrections based on motion feedback to adapt to dynamic environmental changes.
    3. We perform a comprehensive analysis of the framework’s effectiveness in navigating and handling dynamic scenarios in household environments.

## Methodology
### Task Planning
We use GPT-4o, structured outputs, and chain-of-thought prompting to get an accurate sequence of tasks to be performed in the format of a program. 

### Motion Planning
We use A* to determine shortest path to immplement the task and navigation in the VirtualHome Simulator. VirtualHome employs NavMesh to split the layout of a particular room in a grid-like structure. This makes A* a suitable motion planning algorithm to be used.

### Evaluation Methods
We develop scenarios of increasing complexities for evaluation:

    1. Pick up an object
    2. Avoid an obstacle to pick up the object
    3. Choose person for whom its more convenient to pick up the object.
    4. Work with another person to complete a task


<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/1.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/3.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/5.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images, even citations {% cite einstein1950meaning %}.
Say you wanted to write a bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, _bled_ for your project, and then... you reveal its glory in the next row of images.

<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>

The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

{% raw %}

```html
<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/6.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
  <div class="col-sm-4 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/11.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
```

{% endraw %}
