# Smart Multi-Level Parking Optimization

## Overview

This project focuses on optimizing the allocation of vehicles in a multi-level parking system.

Vehicles arrive over time and must be assigned to available parking spaces while respecting constraints such as:

* Space availability
* Vehicle compatibility
* Electric charging requirements
* Capacity limits per level

The goal is to minimize overall user inconvenience, including walking distance, congestion, and inefficient assignments.

---

## Problem Scope

We model:

* A set of vehicles (arrival time, type, duration)
* A multi-level parking structure
* Parking spaces with attributes (size, EV support, location)
* A distance matrix inside the parking facility

---

## Dataset

We use the following dataset for parking demand:

https://www.kaggle.com/datasets/datasetengineer/smart-parking-management-dataset

Since it does not include multi-level structures, a synthetic parking layout will be generated.

---

## Project Structure

```bash
smart-parking-optimization/
├── data/            # Raw and processed data
├── notebooks/       # Exploration and experiments
├── src/             # Core logic (to be defined)
├── README.md
├── requirements.txt
└── main.py
```


---

## TEAM

* Nacer Eddine Missouni
* Yasmine Meriche
* Houaria Djabir
