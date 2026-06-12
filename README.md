# Risk to Action Ambulance Deployment

A project page about translating crash-risk predictions into ambulance deployment decisions under operational constraints.

## Project Website

[View Project Site](https://mah-trigui.github.io/risk-to-action-ambulance-deployment/)

## Overview

This project addresses ambulance placement in Nairobi using a two-layer system:

1. predict crash probability for each road segment × 3-hour window
2. convert the resulting risk surface into 6 ambulance deployment positions

The main point is that the model output was not the final operational output.

## Core Idea

A predictive model estimates risk.

An operational system must allocate constrained action.

In this project, the model predicted where crashes were likely, then a decision layer translated those predicted hotspots into ambulance locations.

## Architecture

![Architecture](images/architecture.jpg)

## Main Design Components

- segment × time analytical base table
- multi-source feature fusion from crashes, roads, traffic, weather, and time
- crash elasticity features for temporal trend
- future speed approximation for deployment period
- top-hotspot clustering into 6 ambulance positions

## Selected Implementation Elements

- road-segment decomposition of the city
- 3-hour time-window modeling
- LightGBM / XGBoost crash-risk prediction
- K-means-based deployment translation layer
- operational output formatting per time slot

## Key Takeaway

**Your model predicts risk. Operations needs actions.**

## Public Scope

This repository shares the modeling architecture, selected implementation logic, and project presentation only.
