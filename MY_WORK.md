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
| **Full Name** | [Farhan Hussein Alonazi] |
| **Student ID** | [446050414] |
| **University Email** | [446050414]@std.psau.edu.sa |
| **GitHub Username** | [Farhan1-alonazi] |
| **Repository Link** | [https://github.com/Farhan1-alonazi/OS-Assignment3-Farhan-Alonazi.git]
 
---

## 🎥 Video Link

**Video Link**: [https://youtu.be/c1n74_oJk9E]

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

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 20, 2026, 8:00 PM]
**What I did**: Forked the starter repository, renamed it, checked that it is public, and set my student ID.

**Details**:
 1- Forked makopt/OS-Assignment3-Starter-481 with my university GitHub account and renamed it to OS-Assignment3-Farhan-Alonazi
2-Checked in Settings that the repository visibility is Public
3- Changed studentID on line 304 to 446050414
 4- Committed and pushed the change: I updated my Student ID at line 304

**Challenges**: I made the commit with my own message, and only later noticed that the README asks for the exact format Set my student ID: [YOUR-ID].

**Solution**: I kept the commit as it was, because changing a commit that is already pushed would rewrite the history of main. I used the README's message format for all my next commits.

**Time spent**: 30 Minutes

---

### Entry 2 - [November 21, 2026, 5:30 PM]
**What I did**: Read the README and the whole SchedulerSimulationSync.java, then ran the original starter and saved its output.

**Details**:My parameters: 13 processes, quantum 2000 ms, 2 CPUs
First run: [CPU-1] picks P1 and [CPU-2] picks P1 at the same time, then IllegalThreadStateException in CPU-2, and the WATCHDOG after 27 s
Verification: 24/26 context switches, 12/13 completed, 36970/40104 ms, 894 busy-waiting polls
Second run: the same race, but this time CPU-1 crashed (905 polls)
Saved both outputs for Question 1

**Challenges**: I did not understand why two CPUs picked P1, and why the ready queue printed after the picks started at P3 instead of P2. The console also showed ? instead of the symbols ➕, ▶ and →.

**Solution**:I followed ReadyQueue.poll() step by step. Both CPUs read the same head (P1) during RaceWindow.pause(), so the second removeFirst() removed P2, which was never executed. 3134 ms (P2's burst time) was exactly the missing service time. The ? characters are a Windows console encoding problem, not a code problem; running chcp 65001 in the terminal fixes them.

**Time spent**: 2 hours

---

### Entry 3 - [November 25, 2026, 2:00 PM]
**What I did**: : Feature 1. I protected the ready queue with a ReentrantLock.

**Details**:
1- Added import java.util.concurrent.locks.ReentrantLock;
2- Declared private final ReentrantLock queueLock in ReadyQueue
3- Wrapped the bodies of add(), poll(), processOf() and snapshot() in queueLock.lock(); try { ... } finally { queueLock.unlock(); }
4- Committed: Feature 1: Protected the ready queue with a ReentrantLock

**Challenges**: I was not sure that snapshot() needed the lock, since it only reads, or where to put unlock() in poll(), which has two return statements.

**Solution**:  snapshot() iterates over list and reads map while other CPUs can modify them, so it is a critical section too (otherwise a ConcurrentModificationException can occur). In poll() I kept both return statements inside the try, because the finally block always runs and releases the lock. After this feature, both CPUs never picked the same process again.

**Time spent**: 5 hour

---

### Entry 4 -- [November 25, 2026, 3:45 PM]
**What I did**: : Feature 2. I protected the three shared statistics with one ReentrantLock per variable.

**Details**: 
1- Declared contextSwitchLock, completedLock and serviceTimeLock in SharedStats
2- Protected incrementContextSwitch(), incrementCompletedProcess() and addServiceTime() with lock() and try/finally
3- Protected the three getters with the same lock as the writer of their variable
4- Committed: Feature 2: Added one ReentrantLock per shared statistics counter

**Challenges**: Choosing between one lock for the three counters and one lock per counter.

**Solution**: The three variables are independent: no method updates two of them together. With separate locks, a thread adding service time does not block a thread incrementing the context switches, and each critical section contains a 1 ms RaceWindow.pause(). I also remembered that a getter must use the same lock as the writer, otherwise it can read in the middle of an update.

**Time spent**: 1 hour

---

### Entry 5 - [November 25, 2026, 4:00 PM]
**What I did**: Feature 3. I replaced busy waiting with a counting semaphore and added a clean shutdown.

**Details**: 
1- Added import java.util.concurrent.Semaphore; and declared readyCount = new Semaphore(0) in ReadyQueue
2- Called readyCount.release() in add() after unlock()
3- Added waitForProcess() (acquire()) and wakeUpAllCpus(n) (release(n)) to ReadyQueue
In CpuWorker.run(): deleted the polling block (if (thread == null), Thread.sleep(20)) and replaced it with waitForProcess(), then a break if all processes are completed, then poll()
At the end of the loop, the CPU that sees the last completion calls wakeUpAllCpus(SharedStats.totalCPUs)
Ran the program 5 times: all four lines ✔ and Busy-waiting polls = 0
4- ommitted: Feature 3: Replaced busy waiting with a counting semaphore and clean shutdown

**Challenges**: When I saved the file, VS Code's formatter split the long comments over two lines (for example the TODO lines in CpuWorker), so the text no longer matched the original lines. I pasted the new code in the wrong place and got compile errors. I was also confused because the file has two run() methods, one in Process and one in CpuWorker.

**Solution**: I located the code by line numbers inside CpuWorker.run() (line 391), not Process.run() (line 297). I replaced exactly the busy-waiting block (lines 396–409) and added the shutdown code under the last TODO comment inside the while loop, then compiled and ran it 5 times. I also understood why the break must come before poll(): a CPU woken by the shutdown signal has no process to take.

**Time spent**: 5 Hour

---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [13 hours]

**Most challenging part**: Feature 3. I had to place the semaphore code in exactly the right place in CpuWorker.run() after the formatter changed the comment lines, and understand why the CPUs need a shutdown signal to terminate.

**Most interesting learning**: The starter did not lose P1, which both CPUs read; it lost P2, which nobody read, because the second removeFirst() removed whatever was at the head at that moment. A race condition can damage data that no thread was even looking at.

**What I would do differently next time**: Start much earlier, write the log entry at the end of each session, and turn off format-on-save before editing code that I have to match line by line.

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

I learned that a race condition happens when threads change shared data and the result depends on their order.
An increment like contextSwitchCount is really three steps (read, add, write), so a thread can be interrupted in the middle.
Code that uses shared data is a critical section and needs mutual exclusion, progress and bounded waiting.
I used ReentrantLock and always put unlock() in finally so the lock is released even after a return.
A counting semaphore counts the processes in the ready queue and blocks a CPU instead of letting it busy-wait.
What surprised me was that the starter lost P2, a process that no CPU even read.
## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The most challenging part was Feature 3, especially stopping the CPUs at the end.
After the last process finishes, nobody calls release(), so a CPU in acquire() would wait forever.
The CPU that sees the last completion must call release(totalCPUs), and a woken CPU must break before poll().
VS Code also split the long comments into two lines, so I pasted my code in the wrong place and got errors.
It was confusing that there are two run() methods, and only the one in CpuWorker had to change.
A mistake here does not give a wrong number, the program just hangs until the watchdog stops it.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I ran the original starter several times and saw that both CPUs picked P1 and P2 disappeared.
I traced poll() on paper with CPU-1 and CPU-2 and found that the second removeFirst() removed P2.
I added the features one by one and ran the program 5 times after each one before committing.
For Feature 3, I used line numbers inside CpuWorker.run() to replace only the busy-waiting block.
I re-read the Chapter 5 slides to understand that a blocked wait() needs a signal() to wake up.
I also made sure that I never call acquire() while holding queueLock, to avoid a deadlock.
## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*
The operating system itself shares ready queues between CPU cores, just like my CpuWorker threads.
In banking, two transfers on the same account can lose money like contextSwitchCount lost updates, so they need a lock.
In seat booking, checking and reserving a seat must be atomic, or two people get the same seat like two CPUs got P1.
A web server with worker threads and a request queue is a producer-consumer system that uses semaphores.
A print spooler uses a counting semaphore for the jobs waiting to be printed.
Databases choose between table locks and row locks, the same granularity choice I made for the statistics.

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

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

In my starter run, all four values were wrong: 24/26, 12/13, 36970/40104 ms and 894 polls.
Both CPUs picked P1, CPU-2 crashed, and P2 was lost (its 3134 ms and 2 quanta are missing).
This is a race in poll(): reading and removing the head are separated by RaceWindow.pause().
On a real machine, the OS can preempt a thread at the same point, or two cores run in parallel.
It is hard to detect because the window is tiny, so the bug appears rarely and randomly.
Verification block of the **original starter**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 26       observed 24       ✘ MISMATCH
  Completed processes                    expected 13       observed 12       ✘ MISMATCH
  Total service time (ms)                expected 40104    observed 36970    ✘ MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 894      ✘ MISMATCH
  ✘ At least one check failed (see the ✘ lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 26       observed 26       ✔
  Completed processes                    expected 13       observed 13       ✔
  Total service time (ms)                expected 40104    observed 40104    ✔
  Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
  ✔ All shared values are consistent.
```

**Explanation of the timeline:**
CPU-1 reads contextSwitchCount = 12 into tmp, then is preempted in RaceWindow.pause().
CPU-2 reads the same value 12 into its own tmp, then is also paused.
CPU-1 writes tmp + 1 = 13.
CPU-2 writes tmp + 1 = 13, overwriting CPU-1's write.
Two quanta started but the counter grew by only 1, so one update is lost; contextSwitchLock fixes this by making read, pause and write one critical section.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

queueLock protects the ready queue, and each counter has its own mutex lock.
I used one lock per variable because the three counters are independent.
The trade-off is more concurrency, but more locks and no snapshot of all three at once.
The queue has its own lock so a CPU never waits during a slow counter update.
Locks give mutual exclusion and progress, but a non-fair lock cannot guarantee bounded waiting.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| [e.g., `ReadyQueue.poll()`] | [lock name] | [reason] |
| [...] | [...] | [...] |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

In the starter, an idle CPU slept 20 ms and polled again: 894 busy-waiting polls.
In my version, an idle CPU is blocked in acquire() and uses no CPU time.
readyCount is the number of processes waiting in the queue, and it starts at 0 (empty queue).
After the 13 initial add() calls, its value is 13.
The last CPU calls release(totalCPUs) to wake the blocked CPUs, or they would wait forever.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
It is the producer-consumer (bounded-buffer) problem, and the ready queue is the buffer.
Producers: main and the CPUs that re-enqueue; consumers: the CPUs that take a process.
**Semaphores for a bounded queue (name and initial value)**:
mutex = 1, empty = K and full = 0.
**Deadlock scenario and prevention**:
A producer holding the mutex waits on empty, while the consumer waits on the mutex: deadlock.
I would break hold-and-wait: wait on the semaphore first, then take the mutex.
## Summary

**Key concepts I understood through these questions:**
1.A non-atomic read-modify-write causes a race condition, and a lock fixes it.
2.Independent variables can have separate locks for more concurrency.
3.A semaphore blocks threads instead of busy waiting.

**Concepts I need to study more:**
1. Fair locks and starvation.
2. Monitors and condition variables.

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
