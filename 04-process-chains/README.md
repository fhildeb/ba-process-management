# Event-Driven Process Chains

## Customer Support Process

Scenario: The process begins with the arrival of a customer inquiry. This is followed by the creation of a quotation. This function can be followed by two events that are mutually exclusive: either a customer order is received or the customer gives a refusal. If a sales order is received, the sales order is processed. The result of this function is a sent order confirmation.

![Customer Support Process EPC](/img/04-customer-support.png)

## Receiving Department

Scenario: Incoming goods processing and production execution: After goods have arrived, they are checked regarding organizational unit and information objects. Depending on the result of the inspection, the goods can be released, blocked or rejected. If the production date of a released good arrives, the production can be carried out. The material is then put away and the production order is "finally confirmed".

![Receiving Department EPC](/img/04-receiving-department.png)

## Ordering Process

Scenario: The process runs through the purchasing department and is triggered by requirements messages from production, materials management or the warehouse. The requirements messages are cumulated. With the help of the SAP module it is checked whether the supplier already exists as a master record. If the vendor master record exists, the purchase order is created and the goods receipt process is triggered. If the vendor master record does not exist, it is created beforehand.
![Ordering Process EPC](/img/04-ordering-process.png)

## Customer Aquisition

A potential customer exists and must be recorded. It could be that the customer shows interest, in which case a customer interest inquiry would be recorded, which would then have to be processed. On the other hand, it can happen that an existing customer shows interest on his own. This interest would have to be processed in the same way as above. After such interest processing, however, the process could also be aborted. Thus one would reject the customer interest. With continuation of the process now an offer for the customer is provided, whereupon the customer accepts or rejects. The customer is then notified of the goods and the delivery order is simultaneously issued to the warehouse.
![Customer Aquisition EPC](/img/04-customer-aquisition.png)

## Customer Interest

A suitable model, which is deposited with the customer interest processing. First, the customer interest register is called, so that you can then compile the product bundle for the customer on the screen. The register reads from the product database. After the product is created, the price is calculated and the article availability is checked at the same time. It may happen that some articles are not available. The customer must then be given a rejection. The process ends here. Otherwise, the customer's interest is successfully processed and the sub-process is completed.
![Customer Interest EPC](/img/04-customer-interest.png)
