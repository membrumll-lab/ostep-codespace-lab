# Chapter 7: CPU Scheduling Analysis

## Q1. SJF and FIFO with Three Equal-Length Jobs

**Workload:** Three jobs, each with a length of 200.

| Scheduling Policy | Average Response Time | Average Turnaround Time | Average Wait Time |
|---|---:|---:|---:|
| FIFO | 200 | 400 | 200 |
| SJF | 200 | 400 | 200 |

**Analysis:**

FIFO runs jobs in their arrival order. SJF runs the shortest job first. Since all three jobs have the same length, both policies produce the same execution order in this workload.

Therefore, FIFO and SJF have identical average response time, average turnaround time, and average wait time for this question.
## Q2. SJF and FIFO with Jobs of Different Lengths

**Workload:** Three jobs with lengths of 100, 200, and 300, in that order.

| Scheduling Policy | Average Response Time | Average Turnaround Time | Average Wait Time |
|---|---:|---:|---:|
| FIFO | 133.33 | 333.33 | 133.33 |
| SJF | 133.33 | 333.33 | 133.33 |

**Analysis:**

The jobs are already arranged in ascending order of length. FIFO executes them in arrival order, while SJF selects the shortest available job first. Both policies therefore produce the same execution order and identical average response, turnaround, and wait times for this workload.
## Q3. Round-Robin Scheduling with a Time Slice of 1

**Workload:** Three jobs with lengths of 100, 200, and 300. The time slice is 1.

| Job | Response Time | Turnaround Time | Wait Time |
|---|---:|---:|---:|
| Job 0 | 0 | 298 | 198 |
| Job 1 | 1 | 499 | 299 |
| Job 2 | 2 | 600 | 300 |
| **Average** | **1.00** | **465.67** | **265.67** |

**Analysis:**

Round-robin scheduling gives each ready job a time slice of 1 before moving to the next ready job. As a result, the response times are 0, 1, and 2 for the three jobs. The jobs receive CPU time in turns, so longer jobs must wait for multiple rounds before completing.
## Q4. When Does SJF Have the Same Turnaround Time as FIFO?

**Answer:**

SJF and FIFO produce the same turnaround times when jobs arrive in nondecreasing order of their lengths, assuming all jobs are available at the start. In this case, FIFO already executes the shortest job first, so both policies use the same execution order.

**Experiment:**

For job lengths of 300, 100, and 200, FIFO has an average turnaround time of 433.33, while SJF has an average turnaround time of 333.33. This shows that when jobs are not arranged from shortest to longest, SJF can reduce the average turnaround time.
## Q5. When Do SJF and RR Have the Same Response Time?

**Answer:**

SJF and RR can have the same response times when the RR time quantum is long enough for each job to finish in one turn, and the jobs are ordered from shortest to longest. In this case, both policies execute the jobs in the same order.

**Experiment:**

For three jobs of length 100, SJF has an average response time of 100. RR with a time quantum of 100 also has an average response time of 100. Therefore, the two policies have the same average response time in this experiment.
## Q6. How Does SJF Response Time Change as Job Lengths Increase?

**Experiments:**

| Job lengths | Response times (Jobs 0, 1, 2) | Average response time |
|---|---|---:|
| 10, 20, 30 | 0, 10, 30 | 13.33 |
| 100, 200, 300 | 0, 100, 300 | 133.33 |
| 1000, 2000, 3000 | 0, 1000, 3000 | 1333.33 |

**Analysis:**

In these workloads, jobs are ordered from shortest to longest, so SJF executes them in that order. The first job's response time is 0. Each later job's response time is the sum of the lengths of all jobs before it. When all job lengths are scaled by a factor of 10, the response times and average response time also scale by a factor of 10. This demonstrates that response time grows with job lengths for these workloads.
## Q7. How Does RR Response Time Change as the Quantum Length Increases?

**Experiments:**

All three jobs have a length of 100.

| Quantum length | Response times (Jobs 0, 1, 2) | Average response time |
|---:|---|---:|
| 1 | 0, 1, 2 | 1 |
| 10 | 0, 10, 20 | 10 |
| 100 | 0, 100, 200 | 100 |

**Analysis:**

As the quantum length increases, the response times of later jobs increase in these experiments. Each job must wait for the jobs scheduled before it to receive their time slices. The first job has a response time of 0, while the last job has the largest response time.

Assuming all N jobs are ready at the same time and context-switch overhead is ignored, the worst-case response time is:

[
T_{\text{response,worst}} = (N-1)\times q
]

where N is the number of jobs and q is the quantum length. For example, with 3 jobs and a quantum of 10, the worst-case response time is (3 - 1) × 10 = 20 time units. This matches the response time of Job 2 in the experiment.