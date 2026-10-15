# Chapter 7: CPU Scheduling

## Overview

This assignment explores CPU scheduling policies using the OSTEP CPU scheduling simulator.

## Scheduling Policies

- **FIFO:** First In, First Out.
- **SJF:** Shortest Job First.
- **RR:** Round Robin.

## Experiments

The experiments cover:

1. Comparing FIFO and SJF with equal job lengths.
2. Comparing FIFO and SJF with different job lengths.
3. Examining Round Robin with a short time quantum.
4. Investigating when FIFO and SJF have the same turnaround time.
5. Investigating when SJF and Round Robin have the same response time.
6. Measuring how SJF response time changes as job lengths increase.
7. Measuring how Round Robin response time changes as the time quantum increases, and deriving a worst-case response-time formula.

## Files

- `analysis.md` contains the experiment results and analysis for Questions 1–7.
- `data/` contains the simulator outputs for each experiment.

## How to Run

Run the simulator from the repository root. For example:

```bash
python3 ext/ostep-homework/cpu-sched/scheduler.py -p SJF -l 100,200,300 -c
```

For Round Robin, specify the quantum with `-q`, for example:

```bash
python3 ext/ostep-homework/cpu-sched/scheduler.py -p RR -l 100,100,100 -q 10 -c
```