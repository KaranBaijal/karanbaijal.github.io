---
layout: page
title: MoneyBall for Basketball NBA
description: Use functional programming (OCaml)
img: assets/img/1.jpg
importance: 3
category: work
---

## Objective
We build an NBA trade machine that allows the user to experiment with hypothetical trades between NBA teams. This project was developed with 3 other collaborators (Caleb Kim, Pranay Gupta, Tinsae Walelign) as part of CS3110: Functional Programming and Data Structures at Cornell University. 

The entire code was developed in OCaml using Functional Programming Principles.

**Github Link:** https://github.com/KaranBaijal/NBA_Moneyball

## Instructions of the Game
We develop a GUI for the user to play with the NBA Trade Machine System. The user will see a list of teams in the NBA, which on selecting, the user can see the list of players available to trade. Data has been scraped from the online NBA Webpage for up-to-date data. We set a limit for number of teams that can be involved in a trade to 4 teams, since NBA trades usually do not involve more teams.

Once the user is satisfied with their team selections, they can click to go on to the next step. There, the user will be able to see a list of the teams they have selected for the trade along with the roster for each team. The user will also be able to click on each player’s name to see a more in depth look at his stats, contract, notable career achievements, age, and other important identifying information.

On selecting a player for trade, we first check if the trade is even viable given the NBA salary cap rules and each player’s contract. If the user tries to submit a trade that is not viable, then they will have a choice: either try another trade from scratch, adjust the existing trade that he/she is trying to pull off, or quit the trade machine.

If the trade is viable, we analyze the trade based using a combination of win shares per 48 minutes (which measures a player’s contributions to his team’s winning when he is on the court) and minutes per game for the previous NBA season. Using this combination, we will be able to determine win shares per game played for each player and add up how many wins each team is projected to gain or lose with each trade. We also look at offense/defense ratings, usage rate, true shooting percentage, APER (adjusted PER), and other metrics.

