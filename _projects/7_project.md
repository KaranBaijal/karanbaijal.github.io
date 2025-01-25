---
layout: page
title: MIDAS
description: Material and Adjective Classification using Haptics and Vision
img: assets/img/4.jpg
importance: 1
category: work
redirect: https://drive.google.com/file/d/1rzpVZlt2BLw1Wf0sOP0_0WX0rACy6Ntr/view?usp=share_link
related_publications: true
---

## Objective
NOTE: This is an extensive work. However, I am detailing all the work that I have done in this paper.

## Introduction

## Haptic Learning

## Vision-Language Models (VLM)
#### CLIP
We aimed to see how well vision would do with material recognition. I initially attempted using OpenAI Clip with our current dataset, which I imported from HuggingFace. I tried a variety of techniques to improve performance. The best-performing model was when I was finetuning the lat 6 layers of CLIP along with a multi-layer perceptrion (MLP) and a Final Connected Layer after CLIP. However, we knew we could do better, especially considering material recognition requires a combination of texture recognition and semantic understanding. 

#### Grounded SAM
To boost performance, I implemented Grounded SAM for our Vision-Language Model to only learn from the object of choice rather than distractor objects. I first applied Grounded DINO to obtain bounding boxes on the object of choice. Then, I applied SAM to segment objects in the bounding box. Lastly, I blackened the entire image outside of the segmented object to remove all distractor objects from the image.

#### GPT-4o VLM
To incorporate semantic understanding of the object, we switched our VLM from CLIP to GPT-4o. 
