# Distributed-Enterprise-Software-Development
Group project for DESD\
Isaiah Denton (24019429)\
Charlie Fram (24017379)\
Syed Shah (24034374)\
Sami Mohamed ()\
Tomos Lock (23022057)

## Sprint One
### Plan and Backlog
| Task | Assigned To | Priority |
|------|-------------|----------|
| Create initial product backlog and sprint plan | Charlie / Tomos | Urgent |
| Create BPMN model representing the enteprise | Everyone | High |
| Identify the two candidate major functionalities | Isaiah | Medium |
| Analyse major business processes and organisational responsibilities | Sami / Syed | Medium |

### Business Analysis
Core Problem: 40 local SMEs/food producers within a 20-mile radius of Bristol face major barriers reaching consumers beyond direct farm gate sales or traditional farmers' markets. Many producers spend up to 15 hours per week managing manual orders via phone and email.

Core Solution: A digital multi-vendor food marketplace that aggregates local produce, handles multi-vendor checkouts, automates split payments and commission deductions, tracks food traceability/allergens, and calculates food miles. 

Commercial Model: A secure payment system must process transaction for single and multi vendor order, distribute weekly payments to respective producers and calculate the networks 5% commission automatically.

### Major Functionalities
1. Multi-Vendor Order Placement, Split Payment & Supplier Fulfilment
    Case Study Requirement: A secure payment system must process transactions for both single and multiple vendor orders, distribute payments to respective producers according to agreed timeframes, and calculate the network's five percent commission automatically. All financial transactions must comply with current data protection and financial services regulations.
2. Weekly Producer Financial Settlement & Commission Distribution
    Case Study Requirement: The platform must execute weekly payment settlements, calculate the 5% network commission automatically, provide audit trails for accounting/tax, and interface with an external payment gateway.

# Business Processes and Organisational Responsibilities

## Business Overview
The proposed digital marketplace connects approximately 40 food producers within 20 miles of Bristol to customers through one online platform. It replaces time-consuming telephone and email ordering with multi-vendor checkout, supplier order management and automated weekly financial settlements. The marketplace earns a **5% commission** on eligible sales.

## 1. Major Business Process: Multi Vendor Ordering, Payment and Fulfilment
**Purpose:** Allow customers to buy from one or several producers in a single secure transaction while ensuring each producer receives the correct order and payment allocation.

**Main activities:**
1. Producers maintain product listings, stock levels, prices, allergen and traceability information.
2. Customers add items from different producers to one basket and place an order.
3. The platform validates the order and sends the payment to an external secure payment provider for processing.
4. The platform records each producer's share of the order and calculates the applicable 5% marketplace commission.
5. Each producer receives their own order details, prepares the goods and updates fulfilment status.
6. The platform informs customers of order progress and manages cancellations, refunds and payment failures.

**Organisational responsibilities:**
- **Producers:** Keep listings accurate, manage stock, meet food information requirements and fulfil orders.
- **Payment provider:** Securely process payments and provide transaction confirmations.
- **Customers:** Provide correct order and delivery/collection information and authorise payment.

## 2. Major Business Process: Weekly Producer Settlement and Commission Distribution
**Purpose:** Pay producers accurately and on schedule while automatically retaining the marketplace's 5% commission and producing reliable financial records.

**Main activities:**
1. The platform records completed transactions and allocates sales to individual producers.
2. It totals each producer's eligible sales for the weekly settlement period.
3. It calculates the **5% network commission** and adjusts for refunds or other agreed deductions.
4. The authorised payment provider executes weekly producer payouts under agreed settlement terms.
5. The platform produces producer statements, commission reports and audit trails for accounting and tax purposes.

**Example:** On £100 of eligible producer sales, the marketplace commission is **£5** and the producer receives **£95**, before any separately agreed fees or adjustments.

**Organisational responsibilities:**
- **Producers:** Provide accurate payment details, review weekly settlement statements, verify commission deductions and report any payment discrepancies.
- **Customers:** Complete secure payments for single- or multi-vendor orders and provide accurate transaction information.
- **Bristol Regional Food Network:** Oversee weekly producer settlements, ensure the automatic calculation and deduction of the 5% commission, maintain financial records and audit trails, manage payment discrepancies, and ensure compliance with relevant financial and data protection regulations.

## 3. Shared Governance and Compliance Responsibilities
- **Bristol Regional Food Network (inferred organisational responsibility):** Oversee marketplace operations, ensure compliance with UK GDPR and relevant financial regulations, maintain accurate transaction records, and ensure secure payment processing through an appropriate payment gateway. During development and testing, only sandbox or simulated payment services must be used.
- **Producers:** Ensure accurate product information, including allergen warnings, organic certification status, best-before dates and food traceability records. Maintain accurate stock availability and fulfil orders within agreed timeframes.
- **Customers:** Provide accurate personal and order information, complete payments securely, and follow agreed delivery or collection arrangements.

## Summary
The two core business processes are **(1) multi vendor ordering, secure payment and supplier fulfilment** and **(2) weekly producer financial settlement and automatic 5% commission distribution**.

**Producers** are responsible for maintaining product information, managing stock, fulfilling orders and reviewing financial settlements. **Customers** are responsible for placing orders, providing accurate information and completing payments. The **Bristol Regional Food Network**, as the assumed marketplace operator, oversees platform operations, financial settlements, commission deductions and regulatory compliance.

### BPMN Model: Strategic Enterprise Overview
![BPMN Model: Strategic Enterprise Overview](images/BRFN%20Strategic%20Enterprice%20Model.png)
Figure 1: Strategic BPMN model showing the producer, marketplace, customer and payment provider pools 
