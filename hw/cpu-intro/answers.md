# OSTEP Chapter 4 Homework Answers

## Q1
- Prediction / 预测: PID 0 runs for ticks 1–5, then PID 1 runs for ticks 6–10. Total time: 10 ticks. Predicted CPU utilization: 100%.
- Reasoning / 理由: Both processes contain five CPU instructions and no I/O. The CPU should remain busy until both processes finish.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q2
- Prediction / 预测: PID 0 uses the CPU for four ticks. PID 1 then starts an I/O operation, waits for five blocked ticks, and handles I/O completion. Predicted total time: 11 ticks.
- Reasoning / 理由: The default I/O operation occupies one CPU tick to start, five ticks waiting, and one CPU tick to finish.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q3
- Prediction / 预测: PID 0 starts I/O at tick 1. PID 1 uses the CPU during ticks 2–5. The CPU is idle at tick 6 while PID 0 remains blocked, and PID 0 handles I/O completion at tick 7. Predicted total time: 7 ticks.
- Reasoning / 理由: SWITCH_ON_IO allows PID 1 to run while PID 0 waits for I/O.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q4
- Prediction / 预测: PID 0 starts I/O at tick 1. Under SWITCH_ON_END, PID 1 does not run during the I/O wait. The CPU is idle during ticks 2–6; PID 0 handles completion at tick 7, then PID 1 runs for four ticks. Predicted total time: 11 ticks.
- Reasoning / 理由: The scheduler switches processes only when the current process finishes, so the other process cannot use the CPU during the I/O wait.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q5
- Prediction / 预测: With SWITCH_ON_IO, PID 1 runs during PID 0's I/O wait. PID 1 finishes at tick 5, and PID 0 handles I/O completion at tick 7. Predicted total time: 7 ticks.
- Reasoning / 理由: Switching on I/O lets another ready process use the CPU while the first process is blocked.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q6
- Prediction / 预测: PID 0 performs three I/O operations. With IO_RUN_LATER, its I/O completion work waits for its turn after other ready processes run. Predicted total time: 31 ticks.
- Reasoning / 理由: Each I/O operation requires a start instruction, five blocked ticks, and a completion instruction. The three CPU-only processes can use the CPU while PID 0 waits.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q7
- Prediction / 预测: The process with three I/O operations resumes immediately when each I/O finishes. Predicted total time: 21 ticks.
- Reasoning / 理由: IO_RUN_IMMEDIATE gives the I/O-completing process priority, allowing it to issue its next I/O without waiting for the other ready processes to finish.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.

## Q8
- Prediction / 预测: For seeds 1, 2, and 3, compare the default behavior, IO_RUN_IMMEDIATE, and SWITCH_ON_END. Immediate resumption may reduce waiting for an I/O-heavy process, while SWITCH_ON_END may leave the CPU idle during I/O waits. The exact trace depends on the seeded instruction lists.
- Reasoning / 理由: The seed determines the CPU/I/O instruction sequence. Scheduling and I/O-completion policies determine when each process runs.
- Verified result / 验证结果: Pending.
- Analysis / 分析: Pending.
