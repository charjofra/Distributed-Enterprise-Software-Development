# Weekly Producer Settlement Model Report

## Overview

The BPMN model represents the marketplace's weekly producer settlement process. It automates the calculation of producer earnings, deducts the marketplace's 5% commission, submits payouts through an external payment service, updates financial records and sends settlement statements.

It also handles reconciliation discrepancies, failed payments and producer disputes.

## Process overview

1. **Weekly trigger:** A timer start event (`R/P7D`) starts the settlement process every seven days.
2. **Identify producers:** A service task retrieves producers with eligible, unsettled orders.
3. **Process each producer:** A sequential multi-instance subprocess runs the settlement workflow once per eligible producer.
4. **Reconcile records:** The platform loads order and payment data and checks that the financial records match. Discrepancies are sent to Finance & Settlement Operations for investigation.
5. **Calculate payout:** The platform calculates gross earnings, the 5% commission and the producer's net payout. Existing checkout commission records are used where possible to avoid double-charging.
6. **Submit payment:** A Send Task sends the payout request to the external payment service. A Receive Task waits for the result, correlated using `settlementId`.
7. **Handle outcome:** Successful payments are recorded in the marketplace ledger and a statement is sent to the producer. Failed payments are sent to Finance for review.
8. **Handle disputes:** Producers manually review their statements and can report discrepancies. These reports trigger a separate marketplace investigation process.

## Technical decisions and reasoning

- **Timer start event:** Automates the weekly schedule without requiring manual initiation.
- **Sequential multi-instance subprocess:** Processes each producer individually, improving traceability and reducing the complexity of concurrent payment handling.
- **Service Tasks:** Represent automated operations such as retrieving records, reconciling data, calculating payouts and updating the ledger.
- **User Tasks:** Assign investigations and failed-payment reviews to finance staff, where human judgement is required.
- **Manual Tasks:** Represent producer activities outside the marketplace's automated workflow.
- **Exclusive gateways:** Direct the process based on conditions such as whether records match or a payment succeeds.
- **Message flows:** Represent communication between the marketplace, producers and external payment service.
- **Settlement correlation:** Uses `settlementId` to ensure payment responses are matched to the correct settlement.

A key financial control is that the producer ledger is updated only after payment success is confirmed. A submitted payment request is not treated as a completed payment.

## Conclusion

The model provides a structured and controlled approach to weekly producer payments. It combines automation with human oversight, separates marketplace responsibilities from external participants and includes exception handling for financial discrepancies and disputes.

Its technical design prioritises traceability, financial accuracy and clear responsibility, providing a foundation for implementing the settlement workflow in Camunda.