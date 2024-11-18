---
layout: page
title: High-Energy Computational Physics
description: Determining a Dark Matter Model through Computational Methods
img:
importance: 3
category: work
---

## Objective

## Boosted Decision Trees
Since the spring of my junior year, I have been involved in experimental particle physics research on the Compact Muon Solenoid (CMS) experiment in Prof. Julia Thom-Levy’s lab. Under Ph.D. student Sam Bright-Thonney, I worked on a search for evidence of dark matter (DM) particles produced in proton-proton collisions at the Large Hadron Collider (LHC). To do so, I trained a machine learning model using boosted decision trees that analyzed large amounts of dark matter signal and Standard Model (SM) background data to determine features, such as momentum and missing energy, and feature values (cuts) that led to the clearest distinction between DM signal and SM backgrounds. As deliverables, I shared the code implementation, generated histograms to understand the model’s performance through signal purity, and analyzed the impact of individual input variables on discrimination power. 

To supplement my research, I self-studied Griffith’s ‘Introduction to Elementary Particles’ and Buckley’s ‘Practical Collider Physics’ to strengthen my theoretical understanding. 

## Isolation Metric
After successfully completing this work, I began working on a new problem the group was facing. The DM model we are searching for predicts a pair of “isolated” electrons coming from the proton collision, meaning that there should be very few other particles measured nearby in the CMS detector. However, we observed minimal distinction between DM signals and SM backgrounds due to a flaw in how isolation is computed for low-momentum electrons. Thus, I began working on designing an algorithm to compute a corrected version of the isolation. I built on top of CERN’s existing public codebase and used specialized LHC physics analysis libraries to implement the algorithm. We expect the new isolation variable to improve signal vs. background discrimination 


## Publication
We aim to publish this research in March 2025 detailing the algorithm’s development, its application to the CMS dataset, and the resulting limits on dark matter models. 
