# Business Process Model and Notation

## Sample BPMN

![Sample BPMN](/img/05-sample-bpmn.png)

## Gateways

Gateways are used for process control and can either show inclusive or exclusive behavior. They can be used to model decisions and lead to branching or merging.

In this project, they are used inclusively.

Scenario: Only intermediate catch events are possible and the task whose event occurs first is selected. If the signal event occurs first, the timer event and message catch event are canceled, continuing with task 4. If the message catch event occurs first, the signal event and the timer are canceled, continuing with task 3. If neither the message event nor the signal event is triggered within 10 minutes, the system continues with task 2.

![Gateways BPMN](/img/05-gateways-bpmn.png)

## Business Rules

Scenario: A company receives an order. Depending on the order quantity and the customer type, a discount is granted. After calculating the discount, the invoice is created. If the quantity is below 500, no discount is given. If quantity is equal or greater than 500 and smaller than 1000, 1% discount will be handed over. In addition, if the customer is from type A, an additional 1% discount will be applied. If quantity is equal or greater than 1000 but lower than 1500, the company even receives a 2% discount. Here, if the customer is type B, an additional 1 % discount will be discount will be applied. Should the quantity be equal or surpass an amount of 1500, a generous discount of 5% is given. An additional 1.5% discount will be granted if customer is from type A.

![Business Rules BPMN](/img/05-business-rules.png)

### Designing a Business Rule Task

Business rules should not be mapped in the BPMN diagram. Instead, a business rule task should be used that describes how to calculate the discount, to reduce chaos within diagrams.

![Business Rule Task](/img/05-business-rule-task.png)

## Credit Score

The creditworthiness of a customer is to be checked. While the check is running, a second request for the same customer may arrive. However, this is not to be processed until the first one has been completed.

### Signal Events

- An Intermediate Signal Catch Event is used to listen for triggered signal throw events. If the process reaches an intermediate signal catch event, it waits until the corresponding signal throw event is triggered.
- An Signal Throw Event is transmitted to all active instances of a process.

![Credit Score BPMN Signals](/img/05-credit-score-signals.png)

### Message Events

- An Intermediate Message Catch Event listens for triggered message throw events. If the process reaches an intermediate message catch event, it waits until a message with the correct name arrives.
- An Intermediate Message Throw Event is sent to a specific receiver or instance and their messages include a name and payload data for identification and instructions.

![Credit Score BPMN Messages](/img/05-credit-score-messages.png)

## Events

Events can occur in three different places in a BPMN diagram: As start event, boundary event of a task and as intermediate event between tasks.

The following diagram showcases various states of a vacation planning:

- The process is triggered at a certain point in time
- It interrupts for at least 1 day between received and processed date
- If it takes too long to review the request, the supervisor is informed.

![Events BPMN](/img/05-events-bpmn.png)

## Best Practices

Best practices include modeling methods that make understanding a business modelling diagram easier.
Within this diagram, lots of mistakes can be found.

![Best Practices Wrong](/img/05-best-practices-wrong.png)

### Following the Core Rules

Within the final diagram, the following rules are applied to align with BPMN principles.

- Avoid flow crossings
- Clearly arrange elements
- Naming Tasks: Object + Verb (infinitive)
- Framing Events: Object + Verb
- Start Events should be labeled with a trigger
- Pools should always be labeled
- XOR Gateways should be labeled with a meaningful question
- Symmetric modeling: each branching gateway has its own merging gateway
- Task elements should have the same size.

![Best Practices Solution](/img/05-best-practices-solution.png)
