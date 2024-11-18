---
layout: page
title: AdaTAMP
description: Multi-collaborative Task and Motion Planning with Feedback Loop
img: assets/img/12.jpg
importance: 1
category: work
related_publications: true
---
## Objective

## Introduction and Related Work
Autonomous agents capable of performing tasks accurately while being able to perceive and respond in a dynamic environment has been an important goal in artificial intelligence (AI) \cite{laird1987soar,russell2016artificial}. Sequential long-horizon planning for embodied agents requires not only reasoning and formulating a series of dependent actions over extended time scales, but also ensuring the feasibility of executing these actions under environment and physical constraints \cite{hartmann2022long,zhou2024isr}. Task and Motion Planning (TAMP) is a methodological framework that hierarchically divides planning into two stages: high-level symbolic planning to reason over abstract action sequences and low-level continuous motion planning to compute feasible trajectories subject to physical constraints \cite{garrett2021integrated,wang2024llm}. Classical solutions like the Planning Domain Definition Language (PDDL) \cite{fox2003pddl2} typically use specific modules to interface symbolic and continuous representations by generating real-valued parameters for symbolic actions and providing numerical goals to the motion planner \cite{emerson1990temporal, jiao2022sequential}. However, these approaches often require manual domain-specific design and struggle with long-horizon task planning and real-time adaptability, limiting generalization in dynamic environments \cite{wang2024llm}.

Recent advancements in Large Language Models (LLMs) \cite{achiam2023gpt,touvron2023llama}, such as GPT-4 \cite{achiam2023gpt}, have demonstrated capabilities in reasoning \cite{shinn2024reflexion,wu2024read}, problem-solving \cite{kim2024language, madaan2024self}, and embodied task planning \cite{huang2022language, song2023llm, wu2023embodied}. LLMs have shown the ability to serve as task planners by decomposing long-horizon tasks into a sequence of sub-tasks based on natural language instructions \cite{liu2024delta}. For instance, Huang et al. translates high-level plans (e.g., “make breakfast”) into mid-level actionable steps (e.g., “open fridge”) using language models \cite{huang2022language}. In another paper, Huang et al. introduces a decoding strategy to construct action sequence executable by language and grounded models for robot manipulation tasks \cite{huang2024grounded}. Some researchers have also proposed iterative self-refinement strategies that refine initial plans through environmental feedback to improve complex sequential decision-making where each mid-level action influences subsequent ones \cite{madaan2024self, sun2024adaplanner, zhou2024isr}. While LLMs perform reasonably well at high-level planning, they often struggle to translate these plans into precise low-level actions (i.e., motion control) and account for real-world constraints and dynamic environments, which must be optimized together for many embodied tasks \cite{chen2024autotamp,choi2024lota}. Wang et al. \cite{wang2024llm} employed pre-trained language models to generate symbolic action sequences and continuous action parameters, and incorporated motion planning feedback to iteratively refine the plan in response to motion failures. Chen et al. \cite{chen2024autotamp} developed a framework that converts few-shot translation of natural language task descriptions into an intermediate task representation through auto-regressive re-prompting for task and motion planning. However, these methods did not effectively explore the integration of \textit{continuous} motion planning necessary for handling complex embodied environments, and lack a robust mechanism for \textit{real-time self-correction} based on motion execution feedback. Additionally, the above methods mainly focus on robot manipulation rather than determining optimal paths for navigating to and completing a long-horizon task ina  dynamic environment with multiple agents and objects.

To address these limitations, we present AdaTAMP, an LLM-based adaptive TAMP framework that combines continuous motion planning with a self-feedback loop for real-time correction to enhance the integration of symbolic task planning and motion execution for embodied agents in household environments. Our contribution can be summarized as follows:
\begin{itemize}
    \item We present the AdaTAMP framework, which integrates symbolic task sequences with continuous motion planning to improve task execution for embodied agents in a multi-agent setting.
    \item We incorporate a self-feedback loop that allows for real-time corrections based on motion feedback to adapt to dynamic environmental changes.
    \item We perform a comprehensive analysis of the framework’s effectiveness in navigating and handling dynamic scenarios in household environments.
\end{itemize}

To give your project a background in the portfolio page, just add the img tag to the front matter like so:

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

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
