---
layout: page
title: High-Energy Computational Physics
description: Determining a Dark Matter Model through Computational Methods
img:assets/img/LHCCollision.jpg
importance: 1
category: work
---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/DMModels.png" title="DM Models" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
  Fig 1. Wide number of potential models to study Dark Matter
</div>

## Introduction
There are a wide number of potential models to study dark matter. The universe supposedly covers 27% of the known universe; however, we know nothing about what dark matter is composed of and how it interacts with the Standard Model - the most successful theory in Particle Physics. One potential model is that of inelastic dark matter. 

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.liquid loading="eager" path="assets/img/Feynmandiag.png" title="Feynman Diagram" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
  Fig 2. Example Feynman diagram of a physics process predicted by inelastic dark
matter at the LHC. Protons collide producing an on-shell dark photon, which decays
to two different dark matter states. The lighter state (denoted \χ1 , in green) escapes the 
detector, while the heavier one (denoted \χ2 , in blue) travels a macroscopic distance
before itself decaying. The decay of the heavy \χ2 state produces an additional light \χ1
particle as well as a pair of soft, narrow muons via an off-shell dark photon.

</div>


## Boosted Decision Trees
Since the spring of my junior year, I have been involved in experimental particle physics research on the Compact Muon Solenoid (CMS) experiment in Prof. Julia Thom-Levy’s lab. Under Ph.D. student Sam Bright-Thonney, I worked on a search for evidence of dark matter (DM) particles produced in proton-proton collisions at the Large Hadron Collider (LHC). To do so, I trained a machine learning model using boosted decision trees that analyzed large amounts of dark matter signal and Standard Model (SM) background data to determine features, such as momentum and missing energy, and feature values (cuts) that led to the clearest distinction between DM signal and SM backgrounds. As deliverables, I shared the code implementation, generated histograms to understand the model’s performance through signal purity, and analyzed the impact of individual input variables on discrimination power. 

To supplement my research, I self-studied Griffith’s ‘Introduction to Elementary Particles’ and Buckley’s ‘Practical Collider Physics’ to strengthen my theoretical understanding. 

![Feature importance](https://github.com/user-attachments/assets/00207bdd-ade1-4d5b-9357-2cc30453bdba)

## Isolation Metric
After successfully completing this work, I began working on a new problem the group was facing. The DM model we are searching for predicts a pair of “isolated” electrons coming from the proton collision, meaning that there should be very few other particles measured nearby in the CMS detector. However, we observed minimal distinction between DM signals and SM backgrounds due to a flaw in how isolation is computed for low-momentum electrons. Thus, I began working on designing an algorithm to compute a corrected version of the isolation. I built on top of CERN’s existing public codebase and used specialized LHC physics analysis libraries to implement the algorithm. We expect the new isolation variable to improve signal vs. background discrimination 


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

## Publication
We aim to publish this research in March 2025 detailing the algorithm’s development, its application to the CMS dataset, and the resulting limits on dark matter models. 
