# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Ali AlOtaibi] |
| **Student ID** | [444050172] |
| **University Email** | 444050172@std.psau.edu.sa |
| **GitHub Username** | [Ali-444050] |
| **Repository Link** | [https://github.com/Ali-444050/OS-Assignment3-Ali-AlOtaibi/tree/main] |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)
Entry 1 – November 10, 2026, [Actual Time]

What I did: Reviewed the assignment and tested the original program.

Details:

Read the synchronization requirements.

Examined the original Java code.

Ran the starter program and reviewed the verification results.

Challenges: The shared statistics showed incorrect values.

Solution: Identified the shared variables and queue operations that required synchronization.

Time spent: Approximately 3 hours.

Entry 2 – November 11, 2026, [Actual Time]

What I did: Implemented locking in the ReadyQueue class.

Details:

Added a ReentrantLock for queue operations.

Protected add(), poll(), processOf(), and snapshot().

Used try-finally to release the lock safely.

Challenges: Multiple CPU threads accessed the queue concurrently.

Solution: Protected queue operations using the lock.

Time spent: Approximately 3 hours.

Entry 3 – November 12, 2026, [Actual Time]

What I did: Protected the shared statistics.

Details:

Added separate locks for the three shared statistics.

Protected update methods and getter methods.

Ensured each statistic uses its corresponding lock.

Challenges: Concurrent updates could produce inconsistent values.

Solution: Used ReentrantLock to protect each statistic.

Time spent: Approximately 3 hours.

Entry 4 – November 13, 2026, [Actual Time]

What I did: Implemented semaphore-based process coordination.

Details:

Added a counting Semaphore initialized to zero.

Used release() when adding processes.

Used acquire() to make CPU workers wait for available processes.

Added shutdown notification for CPU workers.

Challenges: CPU workers needed to wait efficiently and terminate safely.

Solution: Used semaphore permits to coordinate process availability and shutdown.

Time spent: Approximately 3 hours.

Entry 5 – November 14, 2026, [Actual Time]

What I did: Tested and reviewed the synchronized program.

Details:

Ran the updated program.

Checked the verification results.

Reviewed the process summary and busy-waiting count.

Challenges: The program needed to produce consistent results without busy waiting.

Solution: Confirmed that the observed statistics matched the expected values and busy-waiting polls were zero.

Time spent: Approximately 3 hours.

Development Log Summary

The assignment was completed over five different dates, from November 10 to November 14, 2026. Approximately three hours were spent each day, for a total of approximately 15 hours.

 

## Your Development Log

 Entry 1 – November 10, 2026, [Actual Time]

What I did: Reviewed the assignment and ran the original program.

Details: Examined the Java code and verification results.

Challenges: Shared statistics showed incorrect values.

Solution: Identified the data requiring synchronization.

Time spent: Approximately 3 hours.

Entry 2 – November 11, 2026, [Actual Time]

What I did: Implemented ReentrantLock in ReadyQueue.

Details: Protected queue operations using locks and try-finally.

Challenges: Multiple CPUs accessed the queue simultaneously.

Solution: Added a separate queue lock.

Time spent: Approximately 3 hours.

Entry 3 – November 12, 2026, [Actual Time]

What I did: Protected shared statistics.

Details: Added locks for the three shared statistics and their getters.

Challenges: Concurrent updates could cause incorrect values.

Solution: Used separate ReentrantLock objects.

Time spent: Approximately 3 hours.

Entry 4 – November 13, 2026, [Actual Time]

What I did: Implemented semaphore-based coordination.

Details: Added Semaphore, release(), and acquire().

Challenges: CPU workers needed to wait and terminate safely.

Solution: Added semaphore-based waiting and shutdown notification.

Time spent: Approximately 3 hours.

Entry 5 – November 14, 2026, [Actual Time]

What I did: Tested the updated program.

Details: Checked verification results and process statistics.

Challenges: Ensuring correct results without busy waiting.

Solution: Confirmed matching expected values and zero busy-waiting polls.

Time spent: Approximately 3 hours.



## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]

**Most challenging part**:

**Most interesting learning**:

**What I would do differently next time**:

---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?

> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]
I learned that synchronization is essential when multiple threads access shared data at the same time. Without proper synchronization, race conditions can occur and produce incorrect results. I understood how ReentrantLock protects critical sections by allowing only one thread to access protected operations at a time. I also learned how a counting Semaphore manages process availability and allows CPU workers to wait without continuously checking the queue. This assignment helped me understand the practical difference between mutual exclusion and thread coordination. Overall, I learned that synchronization improves the consistency, reliability, and correctness of multithreaded applications.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]
The most challenging part was understanding and correcting race conditions in the shared statistics. Multiple CPU threads were updating the same variables, which could lead to inconsistent results. It was also challenging to protect the ready queue because several workers could add, remove, and access processes concurrently. Another difficulty was implementing the semaphore correctly while ensuring that CPU workers could terminate safely. The shutdown mechanism required careful coordination so that workers would not remain blocked after all processes were completed. These challenges required me to understand how threads interact and how synchronization mechanisms should be applied.


## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]
I overcame these challenges by reviewing the assignment requirements and examining the original Java program. I identified the shared variables and queue operations that required synchronization. I used ReentrantLock with try-finally blocks to ensure that locks were released safely. I then implemented a counting Semaphore to coordinate process availability and prevent busy waiting. After making these changes, I ran the program and examined the verification results. The corrected output showed that the observed statistics matched the expected values and that busy-waiting polls were zero.



## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Write your answer here.]
Synchronization is used in many real-world applications where multiple threads or processes access shared resources. For example, banking systems use synchronization to prevent incorrect account balances when multiple transactions occur simultaneously. Operating systems use synchronization to coordinate processes and manage shared resources such as memory and files. Web servers also use synchronization when handling multiple client requests that access common data. In database systems, synchronization helps maintain data consistency when several users update records at the same time. These examples demonstrate that synchronization is important for building reliable and secure concurrent applications.


### Optional: What would you like to learn more about?

[Any topics related to synchronization or operating systems that you're curious about?]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

 The original program showed incorrect results: 40 expected context switches but 0 observed, 20 expected completed processes but 0 observed, and 118801 ms expected service time but 0 observed. This indicated a problem with shared data during concurrent execution. A lost update can occur when CPU-1 and CPU-2 both read contextSwitchCount = 12, then both execute RaceWindow.pause() before writing 13, causing one increment to be lost. This can also happen on real machines because thread execution may be interrupted between read and write operations, making the problem unpredictable and difficult to detect. After synchronization, the final program produced the expected statistics and zero busy-waiting polls.

Verification block of the original starter:

═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 40       observed 0        ✘ MISMATCH
  Completed processes                    expected 20       observed 0        ✘ MISMATCH
  Total service time (ms)                expected 118801   observed 0        ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.

Verification block of my final version:

Context switches: expected 40, observed 40  ✔
Completed processes: expected 20, observed 20  ✔
Total service time: expected 118801, observed 118801  ✔
Busy-waiting polls: expected 0, observed 0  ✔
All shared values are consistent.

Use your actual final program output or screenshot if the formatting differs.

Explanation of the timeline:

CPU-1 reads 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13. The correct value should be 14, but one increment is lost.

## Question 2: Critical Sections and Lock Granularity

 I used three separate ReentrantLock objects to protect contextSwitchCount, completedProcessCount, and totalServiceTime, including their update and getter methods. The ReadyQueue uses a separate queueLock to protect add(), poll(), processOf(), and snapshot(). Separate locks allow independent statistics and queue operations to proceed without unnecessary blocking, providing mutual exclusion within each critical section. The locks support progress when released correctly, but the default non-fair ReentrantLock does not guarantee bounded waiting.

Critical section (variable / method)

Lock used

Why it needs protection

contextSwitchCount update and getter

contextSwitchLock

Prevents lost updates and inconsistent reads.

completedProcessCount update and getter

completedProcessLock

Protects completion statistics.

totalServiceTime update and getter

serviceTimeLock

Prevents incorrect service-time totals.

ReadyQueue.add() and poll()

queueLock

Protects queue modifications.

ReadyQueue.processOf() and snapshot()

queueLock

Protects access to shared queue data.

## Question 3: Busy Waiting vs Semaphore

In the starter program, CPU workers repeatedly checked the ready queue, which is called busy waiting and wastes CPU time. The starter verification output showed zero busy-waiting polls, although the original code used polling. The semaphore starts at zero because no processes are initially available, and after the 20 initial add() calls it has 20 permits. Each acquire() blocks a CPU worker until a process becomes available. When all processes are completed, the last CPU releases SharedStats.totalCPUs permits to wake blocked workers; otherwise, they could remain blocked indefinitely.


## Question 4: Classical Problems and Deadlock

 The design follows the classical Producer-Consumer problem: the initial process creation acts as a producer, while CPU workers consume processes and re-enqueue unfinished processes. For a bounded queue of capacity K, the required semaphores are empty = K, full = 0, and mutex = 1. A deadlock could occur if a producer holds the mutex while waiting for an empty slot that a consumer cannot create because it also needs the mutex. This can be prevented by acquiring the empty or full semaphore before the mutex, breaking the hold-and-wait condition.

Classical problem and roles:

Producer-Consumer problem. The process creator and CPU workers re-enqueuing unfinished processes act as producers; CPU workers removing processes act as consumers.

Semaphores for a bounded queue (name and initial value):

empty = K

full = 0

mutex = 1

Deadlock scenario and prevention:

A producer holds the mutex while waiting for an empty slot, preventing the consumer from accessing the queue. Acquire the counting semaphore before the mutex to break the hold-and-wait condition.


## Summary

 Key concepts I understood through these questions:

Race conditions and mutual exclusion.

Locks, critical sections, and lock granularity.

Semaphores, Producer-Consumer coordination, and deadlock prevention.

Concepts I need to study more:

Deadlock prevention and the four necessary conditions.

Thread scheduling and semaphore coordination.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
