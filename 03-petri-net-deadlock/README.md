# Dining Philosophers Problem

The [dining philosophers problem](https://en.wikipedia.org/wiki/Dining_philosophers_problem) is a classic synchronization and concurrency problem in computer science, first introduced by Edsger Dijkstra in 1965. The problem presents five philosophers seated around a circular table, each with a plate of spaghetti. Between each philosopher is a single fork, resulting in five forks in total. Philosophers alternate between thinking and eating. To eat, a philosopher must have two forks – one from the left and one from the right. The challenge is to design a petri net schedule that allows all philosophers to eat without deadlock or starvation, ensuring fair access to forks.

## Philosophers Deadlock Dilemmma

Scenario: The philosopher first reaches for the left fork and when he has picked it up, for the right one. Then he begins to eat.

### Singular Flow

![Sequential Singular Flow](/img/03-philosophers-deadlock-1.png)

### Table Flow

![Sequential Table Flow](/img/03-philosophers-deadlock-2.png)

## Philosophers without Deadlock

Scenario: The philosopher reaches for both forks at the same time.

### Singular Flow

![Synchronous Singular Flow](/img/03-philosophers-sync-1.png)

### Table Flow

![Synchronous Table Flow](/img/03-philosophers-sync-2.png)
