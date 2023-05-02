Download Link: https://assignmentchef.com/product/solved-comp304-assignment-2
<br>
Consider the following table of arrival times, burst times and priorities for five processes P0 through P4. The context-switch time is 1 ms. Answer the parts A to D in your report.

<table width="357">

 <tbody>

  <tr>

   <td width="59">Process</td>

   <td width="122">Arrival Time (ms)</td>

   <td width="114">Burst Time (ms)</td>

   <td width="61">Priority</td>

  </tr>

  <tr>

   <td width="59">P0</td>

   <td width="122">0</td>

   <td width="114">14</td>

   <td width="61">2</td>

  </tr>

  <tr>

   <td width="59">P1</td>

   <td width="122">0</td>

   <td width="114">8</td>

   <td width="61">1</td>

  </tr>

  <tr>

   <td width="59">P2</td>

   <td width="122">2</td>

   <td width="114">20</td>

   <td width="61">4</td>

  </tr>

  <tr>

   <td width="59">P3</td>

   <td width="122">4</td>

   <td width="114">4</td>

   <td width="61">3</td>

  </tr>

  <tr>

   <td width="59">P4</td>

   <td width="122">6</td>

   <td width="114">6</td>

   <td width="61">2</td>

  </tr>

 </tbody>

</table>

<h2>Part A</h2>

Draw four Gantt charts illustrating the execution of these processes using (A.1) First Come First Served, (A.2) Shortest Job First (SJF), (A.3) Non-preemptive with priority (lower priority number means higher priority) , and (A.4) RoundRobin (quantum = 6 ms) scheduling. Note that there is context switching overhead.

<h2>Part B</h2>

Calculate the waiting time of each process for each of the scheduling algorithms in Part A. Which of the schedules results in the minimal average waiting time?

<h2>Part C</h2>

Calculate the average turnaround time for each of the scheduling algorithms in Part A. Which algorithm has the lowest average turnaround time?

<h2>Part D</h2>

Based on the previous results, which one of the scheduling algorithms is the best in terms of response time?

<h1>Problem 2</h1>

For this question, use the code skeleton that is included in the assignment folder. In this code, you should complete the parts with a TODO comment and explain why you added/altered the code the way you did in the report. You should not change/add any code outside the explicitly mentioned TODO parts of the skeleton code both for Part A and B.

The provided skeleton code is a sample e-commerce application. The app has <em>N </em>items in stock. Every time the sell() function is called, one item is removed from stock and added to sold (Lines 35 to 50).

<h2>Part A: Racy Code</h2>

In this part, your goal is to fill in the trigger race condition() function so that when you run the code, more items are sold than available. We have added a SLOWDOWN macro in the middle of the critical section to increase the chances of context-switch happening at those points, and consequently, triggering a racecondition. The program will output a message if more stocks than available are sold.

The program creates new threads with the create new thread() function which executes the sell() method in a new thread, so that multiple instances of sell() run in parallel.

Note that you may need to run the program several times for the racecondition to be triggered. Once you observe a race condition, include a screenshot as well as the explanations for the added code in the report.

To compile the code, use gcc code.c -lpthread which links the needed pthread library to the generated binary. You can then run the code via ./a.out.

<h2>Part B: Fixing the race</h2>

Continuing from the code of Part A, you are required to ensure mutual exclusion to eliminate the race condition by using semaphores. APIs that create and use the semaphores are already provided in the skeleton code. Explain the changes in the code in your report.

<h2>Part C: Measuring time</h2>

Measure the time required to run the code for Part A and Part B separately, by adding a time command before program execution, e.g., time ./a.out. Report and explain the time differences.

<h1>Problem 3</h1>

(30pts) A well-known dentist has an office in Sariyer. As she got older, this dentist has a bad habit of taking several naps during day. Her office consists of a waiting room with <em>N </em>chairs and the treatment room can accommodate only one patient at a time. Here are some facts about this dental office.

<ul>

 <li>If there are no patients to be served, the dentist takes a nap.</li>

 <li>If a patient enters the dentist office and all chairs are occupied, then the patient leaves the office.</li>

 <li>If the dentist is busy with a patient but chairs are available, then the patient sits in one of the free chairs.</li>

 <li>If the dentist is asleep, the patient wakes her up. You can assume patients come in through one door and leave through the other. Only one patient can move at a time.</li>

</ul>

Write a monitor (in pseudocode) that coordinates the dentist and her patients. Represents dentist and each patient as separate processes. Explain the purpose of using each semaphore, mutex or condition variable that you include in your solution.

In your implementation, have the following monitor procedures:

<em>get dental treatment: </em>called by the patient, returns when treatment is done <em>get next patient: </em>called by the dentist to serve a patient <em>finish treatment: </em>called by the dentist to let a patient out of the office

<h1>Problem 4</h1>

(5pts) Consider a system consisting of four resources of the same type that are shared by three processes, each of which needs at most two resources. Is this system is deadlock free? Show your work.