# Petri Net Modeling

## Sample Petri Net Drawing

![Sample Petri Net 1](/img/02-sample-petri-net-1.png)

```code
Petri Net N = (S,T,F;m0)

Set of Places: S
Set of Transitions: T
Flow Relation: R
Marker: m

S =     {s1,s2,s3,s4,s5}.

T =     {t1, t2, t3, t4, t5 ,t6, t7}

F = {   (s1, t1),   (s2, t2),   (s2, t3),   (s2, t5),
        (s3, t4),   (s4, t6),   (s5, t7),   (t1,s2),
        (t2,s1),    (t3,s3),    (t4,s5),    (t5,s4),
        (t6,s5),    (t7,s2)     }

m0 =    m(s1)
```

![Sample Petri Net 2](/img/02-sample-petri-net-2.png)

## Petri Net Transition

```code
Petri Net P = (S, T, F)

Set of Places: S
Set of Transitions: T
Flow Relation: R
Marker: m

S =     {A, B, C, D}

T =     {f, g, h}

F = {   (A, f),     (A, g),     (f, B),     (g, C),
        (B, h),     (C, h),     (h, D)      }

Formula = F ⊆ S × T ∪ T × S

m = S → IN ∪ {0} present at:    M(A) = 1    M(B)=2
                                M(C)=0      M(D) = 3
```

![Petri Net Transition](/img/02-petri-net-transition.png)

## Computer Printer Allocation

Scenario: A computer is connected to a printer. The computer sends print jobs to a queue. If the queue is not empty, the printer removes an item from the queue and prints it.

### Single Printer Computer Setup

```code
1. The computer P0 sends a print job T0 to the queue (P1).
2. Feedback from T0 to P0 allows the computer to continue and send more print jobs.
3. If there is a print job or jobs in the queue, so there are marks in P1.
4. T1 can fire when the printer is ready (P3 is marked).

1. The printer prints when P2 is marked.
2. If the printer is currently processing a job (P2 is marked), there is no mark in P3.
3. The printer cannot execute a new job (T1 cannot fire), even if there are jobs in the queue.
4. P1 still contains at least one mark. After printing, T2 switches.
5. The status "ready" (P3 is marked) is reached.
6. The next print job can be fetched and processed.
```

![Computer Printer 1](/img/02-computer-printer-1.png)

### Shared Printer Setup

```code
Extended Model with two users sharing a printer.
```

![Computer Printer 2](/img/02-computer-printer-2.png)

### Multi-Print Setup

```code
Extended Model with three users sharing two printers.
```

![Computer Printer 3](/img/02-computer-printer-3.png)

## Railroad Petri Net

Scenario: A signal system for rail traffic ensures that only one train is allowed to enter a particular section of track at any one time. For this purpose, two signals are controlled, each of which can release or block the entry. Both signals shall never release the entry at the same time.

```code
This concept uses mutual exclusion (Mutex Semaphore Sheme.)
It can be considered as a design pattern.
```

![Railroad Petri Net](/img/02-railroad-petri-net.png)

## Car Sharing Petri Net

Scenario: A family with three members has one car and two car keys. The father wants to use the car to go fishing, the mother to go to work and the daughter to visit her boyfriend. Each family member needs a car key and the car for this purpose. After one family member fulfilled their goal, the car key and the car are returned.

![Car Sharing Petri Net](/img/02-car-sharing-petri-net.png)
