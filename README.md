# Smart Multi-Level Parking Optimization

Project 4 - *Combinatorial Optimization & Metaheuristics*

Cars arrive at a multi-level car park through the day and each must be given a bay,
respecting **size** (a large car needs a large bay), **EV charging** (electric cars prefer a
charger) and **staff preference** (staff prefer bays near the exit). The objective is to
**park as many cars as possible** and, among parked cars, **minimise total inconvenience**
(walking distance + unmet preferences).

## The core constraint: the system is *online*

At time **t** we know only the cars that have already arrived — never the future, and not
even the current car's parking duration. Every decision is made the instant a car arrives
and can never be undone.

Because several cars often arrive at the **same minute** (this data has 268 such minutes,
plus one opening minute with 30 simultaneous cars), the real decision at each instant is a
**min-cost assignment** of *that minute's* cars to the bays free *right now* — no future,
no durations, no time-interval reasoning. This is the problem all five methods solve.

## Notebook - `main.ipynb`

| Part | Author | Content |
|------|--------|---------|
| **Part 1** | Yasmine | the five assignment solvers (Greedy, ILP, Branch & Bound, Genetic Algorithm, Simulated Annealing) + design justification, compared on one contended instant |
| **Part 2** | Houaria | the online day-long simulation across all 10 car parks + comparison and interpretation |

Run top to bottom. Figures are written to `viz/`.

## Data - `data/`

- `vehicles.csv` — 1000 cars: type, arrival/departure (minute of day), user type, EV flag.
- `parking1.json` … `parking10.json` — 10 car-park layouts (98–486 bays, 1–4 floors), each
  bay with size, charger flag and distance to exit.
- `data_prep.ipynb`, `parking layout.pdf`, `IIoT_Smart_Parking_Management.csv` — how the
  vehicle set was derived from the source Kaggle dataset.

## Requirements

```bash
pip install -r requirements.txt
```

`pulp` is **optional**: it powers the exact ILP method. Without it, every ILP step is
skipped automatically and the rest of the notebook still runs (Branch & Bound remains as the
exact reference).

## Team

Nacer Eddine Missouni · Yasmine Meriche · Houaria Djabir
