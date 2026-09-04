---
title: "NBA Playoff Prediction Tool"
excerpt: "Predict NBA playoff performance by using player-interaction data and deep learning."
collection: portfolio
permalink: /project/NBA-Playoff-Prediction-Tool/
---

## Overview

This team project explores how player-interaction data can be used to predict NBA playoff performance.

We transformed player cooperation data into heatmap representations and developed a dual-branch convolutional neural network (CNN) to predict the number of playoff wins for each team.

## Methodology

The modeling pipeline consists of four main stages:

1. Collect game and player data through the NBA API.
2. Construct heatmaps based on shared playing time and shared plus-minus performance between players.
3. Process the two heatmaps using separate pretrained ResNet-18 branches.
4. Predict the expected number of playoff wins and convert the predictions into relative championship probabilities.

The model was implemented in Python using PyTorch.

## Model Development

The dual-branch architecture allows the model to capture two complementary aspects of player cooperation: the frequency with which players appear together and the effectiveness of their combination on the court.

<img width="1200" height="1000" alt="Atlanta_Hawks_201617_shared_minutes" src="https://github.com/user-attachments/assets/321e3404-aeb0-4f24-8953-d73a37be5f6b" />

<div style="display: flex; gap: 20px; flex-wrap: wrap;">

<div style="flex: 1; min-width: 300px;">
<img width="1200" height="1000" alt="Atlanta_Hawks_201718_shared_pm_per_min" src="https://github.com/user-attachments/assets/cdd7b931-ffeb-4530-8238-50cfe4eabc67" />
</div>

<div style="flex: 1; min-width: 300px;">
<img width="1200" height="1000" alt="Boston_Celtics_202324_shared_pm_per_min" src="https://github.com/user-attachments/assets/53a644c3-7953-4e3e-b32f-e4a05a14e3b4" />
</div>

</div>

The model was trained using MSE loss and the AdamW optimizer, with early stopping based on validation performance.

<img width="556" height="443" alt="Loss curve" src="https://github.com/user-attachments/assets/74e7272d-1b96-4ca7-be80-b7701bffab9c" />


To evaluate the model on unseen seasons, the data were divided by season rather than randomly across team-season observations.

## Results

The model produces predicted playoff-win values for each team and converts these predictions into relative championship probabilities.

<img width="1007" height="580" alt="預測結果" src="https://github.com/user-attachments/assets/e16f775f-23c9-4a00-a6d1-2c9a0515091f" />

An interactive visualization allows users to compare the estimated championship probabilities across teams and seasons.

## Reflection

This project strengthened my interest in machine learning and, more importantly, raised questions about how predictive models should be evaluated when the goal is to generalize to future observations.

It also motivated me to explore the statistical foundations behind model evaluation, generalization, and probability estimation.

[View the project on GitHub](https://github.com/Allen9102/NBA-Playoff-Prediction-Tool)
