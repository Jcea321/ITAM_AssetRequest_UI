# ITAM Asset Request - Demo Scenario Flow
### Prototype v6.0 | Client Presentation Guide

---

## Overview

This document walks through multiple real-world scenarios that demonstrate how the Asset Request module works from end to end. Each scenario follows a character through a realistic situation, told as a narrative so stakeholders can easily picture how the system fits into everyday operations.

The system is built around two distinct roles -- **Asset Requestor** and **Asset Manager** -- each with their own permissions, views, and capabilities.

---

## Role Definitions

### Asset Requestor

The Asset Requestor is any employee or consultant who needs to request hardware. When they log into the ITAM system, they only see the **My Requests** view. They do not have access to the Manage Requests section at all -- the navigation option is not visible to them, and even if they tried to access it directly, the system would block them.

What they can do:
- Submit new asset requests for themselves (as an Employee or Consultant)
- View their own request history and current statuses
- Cancel their own requests, but only if the request is still in Pending status
- View the detail and timeline of any of their own requests
- Search, sort, and group their own request list

What they cannot do:
- See other people's requests
- Access the Manage Requests view
- Approve, reject, or take any administrative action on any request
- Fulfill or place any request on hold

### Asset Manager

The Asset Manager is the IT administrator or team lead responsible for reviewing and processing asset requests across the organization. When they log in, they see both the **My Requests** view and the **Manage Requests** view, because a Manager is also a person who may need to request hardware for themselves.

On the My Requests side, the Manager behaves exactly like a Requestor -- they can submit their own requests, view their own history, and cancel their own pending requests. Their own requests still go through the normal approval flow and are not auto-approved, because every request must follow the same process for compliance and audit purposes.

On the Manage Requests side, the Manager has access to five tabs:
- **Pending Requests** -- New requests awaiting initial review
- **Approved Requests** -- Requests that have been approved and are ready for fulfillment
- **On Hold** -- Requests that were approved but cannot be fulfilled right now (e.g., out of stock, vendor delay)
- **Completed Requests** -- All requests that have reached a final state (Fulfilled, Rejected, or Cancelled)
- **All Requests** -- A master view of every request across all statuses, useful for searching and reporting

What they can do (in addition to Requestor capabilities):
- View all requests from all employees and consultants
- Approve or reject pending requests
- Mark approved requests as Fulfilled or place them On Hold
- Move On Hold requests to Fulfilled when stock becomes available
- Add remarks at every decision point for audit trail
- Search, sort, filter, and group across all organizational requests
- View employee details, current asset assignments, and request timelines

---

## Scenario 1: The New Laptop Request (Asset Requestor - Happy Path)

Juan Dela Cruz is a Senior Developer in the Software Development department based at Manila HQ, 12th floor. His laptop is five years old, and lately it has been crashing in the middle of compilation. He can barely run his development tools anymore, and it is starting to affect his sprint deliverables. He decides it is time to formally request a replacement.

Juan logs into the ITAM system. Because his account is set up as an Asset Requestor, his sidebar shows only the My Requests option under the navigation menu. There is no "Manage Requests" link anywhere in his interface -- that section simply does not exist for his role.

He lands on his **My Requests** dashboard. Right away, he can see a summary of all his past requests at the top -- how many are pending, how many have been approved, and how many were rejected. He clicks the **+ Add** button on the toolbar to start a new request.

The New Asset Request form opens. The person type is already set to **Employee**, and he selects his name from the dropdown. The moment he picks his name, the system automatically pulls in his details from the HR data source -- his department, job title, email, phone number, office location, and even his direct manager, Pedro Reyes. He does not have to type any of that manually.

He selects **Laptop** as the asset category from a list of 12 hardware types, sets the priority to **High** because his work is significantly impacted, and picks **February 15, 2025** as his needed-by date. The date picker will not let him select any date in the past, so there is no risk of entering an invalid deadline.

In the justification field, he types a detailed explanation about the age of his current laptop, the frequent crashes, and the slowdown during compilation. As he types, a character counter at the bottom of the field updates in real time -- the system requires at least 20 characters to ensure every request has a meaningful justification, with a maximum of 2,000 characters.

He clicks **Submit Request**. The form validates everything -- all required fields are filled, the justification meets the minimum length, the date is valid -- and the request is created. He is taken back to his My Requests view, where his brand-new request now appears at the top of the list with a yellow **Pending** badge and an auto-generated ID: **REQ-2025-0042**.

Juan does not know who will review his request, and he does not need to. He just knows it has been submitted and he can track it from his dashboard.

---

## Scenario 2: The Consultant Who Needs a Monitor (Asset Requestor - Consultant)

Maria Reyes is a UI/UX Consultant from Vendor-A, embedded with the Software Development team at Manila HQ. She sits in the Contractor Area on the 12th floor and reports to Juan Dela Cruz. She has been struggling with her single-screen setup -- switching between Figma, the browser, and multiple spreadsheets all day long is slowing her down. She needs a secondary monitor.

Maria logs into the ITAM system. Like Juan, she only sees the My Requests view -- consultants have the same Asset Requestor role. She clicks **+ Add** to create a new request and switches the person type toggle from **Employee** to **Consultant**. The moment she does this, the person dropdown reloads entirely -- instead of showing the company's internal employee list, it now pulls from the Vendor Management data source and displays only consultants. She selects her name, and the metadata panel populates with her details, including her vendor email domain (maria.reyes@vendor-a.com) and her Contractor Area office location.

A clear **Consultant** badge appears next to her name, visually distinguishing her from regular employees throughout the entire system. She fills in the rest of the form -- Monitor, Medium priority, needed by March 1, 2025 -- and submits. Her request is created with the consultant tag visible on the card, so when it reaches the Asset Manager's queue, they can immediately tell this request came from a contractor rather than a full-time employee.

---

## Scenario 3: Checking History and Cancelling a Request (Asset Requestor - Self-Service)

A few days later, Juan Dela Cruz logs back in to check on his requests. His My Requests dashboard shows his full history at a glance. The statistics panel at the top tells him he has 5 total requests: 2 are still pending, 1 has been approved, and 1 was rejected. He also has a fulfilled request from earlier in the month.

He wants to quickly find his laptop request, so he types "laptop" into the search bar on the toolbar. The list filters instantly in real time -- no page reload, no waiting -- and only his laptop-related requests appear. He clears the search and decides to try grouping his requests by status instead. He clicks the **Group By** dropdown and selects **Status**. His requests immediately reorganize into clear sections: Pending at the top, then Approved, Fulfilled, and Rejected.

Curious about his old keyboard replacement that was already fulfilled, he clicks **View** on that request card. A detail modal opens showing all the request information on the left, and on the right, a **Timeline** panel that visually traces the request through every stage -- Submitted, Reviewed, Approved, and finally Fulfilled -- with dates and who acted on it at each step.

Then Juan remembers something. His pending monitor request -- he had submitted it a while back, but his team recently received a batch of monitors through a separate procurement. He no longer needs it. He clicks the **Cancel** button on that pending request. A confirmation dialog appears, warning him that this action cannot be undone. He confirms, and the request immediately changes to a gray **Cancelled** badge. The statistics panel updates in real time -- pending count drops by one.

He notices that the Cancel button only appears on requests that are still Pending. His approved, on hold, and fulfilled requests do not have that option -- once a request has moved past the Pending stage, only the Asset Manager controls what happens next.

---

## Scenario 4: The Asset Manager Reviews and Approves a Critical Request

Meanwhile, on the other side of the system, Grace Tan is the IT Asset Manager. When she logs in, her sidebar shows two navigation sections: **My Requests** (for her own personal hardware needs) and **Manage Requests** (for her administrative role). She clicks on Manage Requests.

She lands on the **Pending Requests** tab, which shows four requests waiting for her review. The statistics panel at the top gives her a quick overview -- total requests across the system, how many are pending her review, and the running counts of approved, on hold, and completed requests.

She sorts the pending list by **Priority** in descending order. The most urgent request floats to the top: **REQ-2025-0040**, a Critical-priority Laptop request from Antonio Santos, a Systems Administrator in IT Infrastructure. His justification reads that his laptop is completely non-functional after a hardware failure and he is unable to work at all without an immediate replacement.

She clicks **View** to open the full admin detail modal. This view is more detailed than what the Requestor sees -- in addition to the request information, she can review Antonio's employee profile (department, job title, office, manager) and, importantly, a **Current Assets** panel that shows what hardware Antonio already has assigned to him. This helps her make an informed decision -- she can see whether he already has a backup machine or whether this is truly his only device.

Satisfied that the request is legitimate and urgent, she closes the view and clicks **Approve**. The Approve modal opens with a summary of the request -- ID, employee name, asset type, and priority. There is an optional remarks field where she types: "Approved. Expedited due to critical priority. Procurement to source replacement within 48 hours." She clicks **Confirm Approve**.

The request immediately disappears from the Pending tab and the pending count decreases. It now lives in the **Approved** tab, where it sits with a green **Approved** badge, waiting for the next step -- fulfillment.

On Antonio's side, when he opens his My Requests view, he sees his request has changed from Pending to Approved, and he can read Grace's remarks. He knows his request has been authorized and someone is working on getting him a new laptop.

---

## Scenario 5: The Asset Manager Rejects a Request

Still on the Pending tab, Grace looks at the next request: **REQ-2025-0039**, a Low-priority Storage request from Carlo Lim, a Data Analyst. Carlo is asking for an external SSD to back up project files and development environment snapshots. It is a nice-to-have, not a necessity, and the current quarter's budget is tight.

She clicks **Reject**. The Reject modal opens with the request summary, but this time, the rejection reason field is mandatory -- the system will not let her reject a request without providing an explanation. She tries clicking Confirm without typing anything, and a validation error appears reminding her that a reason is required.

She types: "Budget constraints for the current quarter. External storage is not classified as essential hardware under the current policy. Please re-submit during the Q2 2025 budget cycle." She clicks **Confirm Reject**.

The request is removed from the Pending tab. It moves directly to the **Completed** tab with a red **Rejected** badge, because a rejection is a final decision -- no further action is needed. The rejection reason is displayed directly on the request card, so there is full transparency.

On Carlo's side, he can see exactly why his request was denied and knows when he can try again. This mandatory rejection reason ensures that employees are never left wondering what happened -- every denial comes with a clear explanation.

---

## Scenario 6: Fulfilling an Approved Request (Approved Tab)

Grace switches to the **Approved** tab. Here she sees all the requests she has approved that are waiting to be fulfilled -- assets that need to be sourced, picked from inventory, and delivered to the requesting employee.

Antonio Santos's critical laptop request is at the top. Procurement has confirmed that there is a ThinkPad X1 Carbon Gen 11 available in the warehouse, already imaged and ready to deploy. Grace clicks the **Fulfill** button on Antonio's request.

A Fulfill modal opens showing the request summary. There is a remarks field where she types: "Fulfilled. Asset ITAM-LT-0112 (ThinkPad X1 Carbon Gen 11) assigned and delivered to Antonio Santos at Manila HQ - 10F. Old asset ITAM-LT-0034 retrieved for disposal." She clicks **Confirm Fulfill**.

The request moves from the Approved tab to the **Completed** tab with a blue **Fulfilled** badge. The timeline now shows every stage of the journey with dates and actors: Submitted > Approved > Fulfilled. On Antonio's side, his My Requests view reflects the change immediately -- he can see the blue Fulfilled badge and the fulfillment remarks, including the exact asset tag that was assigned to him.

---

## Scenario 7: Approved but Out of Stock -- Placing a Request On Hold

Elena Villanueva, a QA Lead in the Quality Assurance department, submitted a request for a new Laptop three weeks ago. Grace reviewed it, found it justified, and approved it with the remark: "Approved. Standard laptop to be issued from current inventory."

Now Grace goes to the Approved tab to process Elena's request, but when she checks with procurement, she discovers that the approved laptop model is completely out of stock. The last batch was depleted by a recent onboarding wave, and the next shipment from the vendor is not expected for another four to six weeks.

Grace cannot fulfill the request because there is no physical asset to assign. But the request is still valid and authorized -- she does not want to reject it. This is where the **On Hold** action comes in.

She clicks the **On Hold** button on Elena's request. An On Hold modal opens with a remarks field where she types: "Asset currently out of stock. Procurement has placed a backorder with the vendor (PO-2025-0088). Estimated restock: 4-6 weeks. Employee has been notified via email." She clicks **Confirm On Hold**.

The request moves from the Approved tab to the **On Hold** tab with an orange **On Hold** badge. This is a distinct status -- it is not Pending (which means awaiting review), and it is not Approved (which means ready to fulfill). On Hold specifically means: the request has been authorized, but fulfillment is blocked by an external factor like stock availability, vendor delays, or budget release timing.

On Elena's side, when she checks her My Requests dashboard, she sees her request now has an orange On Hold badge instead of the green Approved one. She can read the admin's remarks and knows exactly what is happening -- the laptop is on backorder, a purchase order has been placed, and the estimated wait is four to six weeks. She does not need to send a follow-up email or chase anyone down.

---

## Scenario 8: Stock Arrives -- Moving from On Hold to Fulfilled

Six weeks later, procurement notifies Grace that the laptop shipment has arrived. The ThinkPad X1 Carbon Gen 11 units are in the warehouse, imaged and ready to deploy.

Grace opens the **On Hold** tab in the Manage Requests view. Elena Villanueva's request is sitting there with the orange On Hold badge. Grace clicks the **Fulfill** button on the request.

A Fulfill modal opens. The system requires her to add a remark -- this is mandatory when fulfilling from On Hold, because there needs to be a clear record of when the hold was resolved and what asset was assigned. She types: "Stock received on Feb 10, 2025. Asset ITAM-LT-0118 (ThinkPad X1 Carbon Gen 11) assigned and ready for pickup at IT Service Desk, Manila HQ - 10F. Employee notified." She clicks **Confirm Fulfill**.

The request moves directly from On Hold to the **Completed** tab with a blue **Fulfilled** badge. The timeline now shows the full journey with an extra step: Submitted > Approved > On Hold (with reason) > Fulfilled (with remark). Every decision, every delay, and every resolution is captured in the audit trail.

On Elena's side, her My Requests view finally shows the blue Fulfilled badge. She can see the remark telling her where to pick up her new laptop, and the timeline shows the complete story -- including the six-week hold and the reason for it.

---

## Scenario 9: The Asset Manager Submits Their Own Request

Grace Tan is not just an Asset Manager -- she is also a person who uses hardware every day. Her headset has been dropping audio during Teams calls, and she needs a replacement.

She switches from the Manage Requests view to her **My Requests** view using the navigation sidebar. This side of the system looks exactly the same as what any Asset Requestor sees -- her own personal request history, her own statistics panel, and the same + Add button.

She clicks **+ Add** and fills out the form: Headset, Medium priority, needed by March 15, 2025, with a justification explaining the audio issues during meetings. She submits the request.

Here is the important part: even though Grace is an Asset Manager who can approve other people's requests, **her own request is not auto-approved**. It enters the system with the same yellow Pending badge as everyone else's. It appears in the Pending tab of the Manage Requests view, where it sits alongside requests from other employees.

This is by design. Every request must follow the same approval flow regardless of who submitted it. If Grace's organization has another Asset Manager, that person would review and approve Grace's request. If Grace is the only manager, the system still enforces the workflow -- she would need to consciously go to the Manage Requests view, find her own request in the Pending tab, and approve it with remarks, creating an audit trail that shows the same person submitted and approved the request. This transparency is critical for compliance -- auditors can see exactly what happened and flag any self-approvals for review.

On her My Requests side, she tracks her headset request the same way any Requestor would. On her Manage Requests side, she continues processing everyone else's requests as usual. The two views are completely separate, and her role as a Manager does not give her any shortcuts or special treatment for her own requests.

---

## Scenario 10: Managing a Flood of Requests (Toolbar Power Features)

It is the start of a new quarter, and Grace's Pending tab is filling up fast. Multiple departments have submitted requests at once -- new hires need laptops, the design team wants monitors, a few developers are requesting RAM upgrades, and there are several accessory requests for keyboards and mice.

She opens the **All Requests** tab to get the full picture across every status. She starts by sorting by **Employee** to see if anyone has submitted multiple requests that could be bundled together. She toggles the sort direction with the arrow button to flip between ascending and descending.

Then she switches to sorting by **Needed By Date**, which pushes the most urgent deadlines to the top. She can immediately see which requests are time-sensitive and which ones have flexible timelines.

Next, she tries **Group By Status**. The entire list reorganizes into clear visual sections -- Pending, Approved, On Hold, Fulfilled, Rejected, and Cancelled -- each with its own header. She switches to **Group By Category** and can now see the distribution at a glance: five laptop requests, three monitors, two memory upgrades, and a handful of accessories. This tells her she might want to consider a bulk laptop purchase order instead of processing them one by one.

She groups by **Priority** and the Critical and High items stand out immediately, separated from the Medium and Low requests below.

Finally, she types "Juan" into the search bar. The list instantly filters to show only Juan Dela Cruz's requests. She clears it and types "laptop" -- now she sees every laptop request across the organization, regardless of who submitted it. The item counter on the toolbar updates in real time, showing something like "Showing 5 of 12 requests," so she always knows how many results she is looking at versus the total.

---

## Scenario 11: The Completed Tab -- A Full History of Final Decisions

At the end of the month, Grace wants to review everything that has been resolved. She opens the **Completed** tab in the Manage Requests view. This tab shows every request that has reached a final state -- regardless of how it got there.

She sees requests with three different badges:
- **Fulfilled** (blue) -- Requests that were approved and successfully delivered. Antonio's laptop, Juan's keyboard, and several other items are here with their asset tags and fulfillment remarks.
- **Rejected** (red) -- Requests that were denied with a reason. Carlo's storage request is here with the budget explanation.
- **Cancelled** (gray) -- Requests that were withdrawn by the employees themselves before review. Juan's monitor request is here -- he cancelled it because his team received monitors through a different channel.

She uses the **Group By Status** option to separate them visually. The fulfilled requests group together, the rejections group together, and the cancellations group together. This gives her a clean view for monthly reporting -- she can quickly count how many requests were fulfilled versus denied, and whether any patterns emerge (like a high rejection rate in a particular category suggesting a policy issue, or a high cancellation rate suggesting employees are finding alternative channels).

She can also search across the completed requests. She types "laptop" and sees every laptop request that has been closed out -- whether fulfilled, rejected, or cancelled. This is useful when procurement asks how many laptops were deployed in a given period, or when management wants to understand the demand for a specific asset type.

---

## Scenario 12: The Full Journey -- Request to Fulfillment (End-to-End Lifecycle)

To tie everything together, here is the complete lifecycle of a single asset request, showing how it flows through the system from start to finish, touching both roles and all five tabs.

It begins when an Asset Requestor submits a request from their My Requests view. They fill out the form, select their asset category and priority, write a justification, and hit submit. The request is created with a **Pending** status and a yellow badge. The Requestor can see it in their My Requests dashboard, and the Asset Manager can see it in the **Pending** tab.

The Asset Manager reviews the request. She opens the detail view, checks the employee's information and current asset assignments, reads the justification, and makes a decision. She has two options: Approve or Reject.

If she **rejects** it, she provides a mandatory rejection reason. The request moves to the **Completed** tab with a red Rejected badge. The Requestor sees the rejection and the reason in their My Requests view. This path is final -- no further action is needed.

If she **approves** it, she can optionally add remarks. The request moves to the **Approved** tab with a green badge. Now the Asset Manager has a second decision to make from the Approved tab: Fulfill or On Hold.

If the asset is **in stock and available**, she clicks Fulfill, adds a remark with the asset tag and delivery details, and the request moves to the **Completed** tab with a blue Fulfilled badge. The Requestor sees the fulfillment details and knows exactly which asset was assigned.

If the asset is **out of stock or delayed**, she clicks On Hold, adds a remark explaining the situation (backorder details, estimated restock date). The request moves to the **On Hold** tab with an orange badge. The Requestor can see the hold reason in their view and knows the request is still valid but waiting on logistics.

When the stock finally arrives, the Asset Manager goes to the **On Hold** tab, clicks Fulfill on the request, adds a mandatory remark documenting the resolution, and the request moves to the **Completed** tab with a blue Fulfilled badge. The full timeline now shows every stage, including the hold period.

At any point before the request is reviewed, the Requestor can **cancel** their own request. It moves directly to the **Completed** tab with a gray Cancelled badge and is removed from the Manager's Pending queue.

And throughout all of this, the **All Requests** tab shows everything in one place -- every request, every status, every person -- for searching, filtering, and reporting.

```
  ASSET REQUESTOR                  ASSET MANAGER                    SYSTEM
  ───────────────                  ─────────────                    ──────
        |                                |                            |
        |  Submit Request                |                            |
        |  (My Requests view)            |                            |
        |------------------------------->|                            |
        |                                |                            |
        |  Status: PENDING               |  Sees in Pending tab       |
        |  (Yellow badge)                |  Reviews request:          |
        |                                |  - Employee info           |
        |                                |  - Current assets          |
        |                                |  - Justification           |
        |                                |                            |
        |                    .----- DECISION -----.                   |
        |                    |                    |                   |
        |                APPROVE              REJECT                  |
        |              (remarks opt.)      (reason mandatory)         |
        |                    |                    |                   |
        |                    |           Status: REJECTED             |
        |                    |           (Red badge)                  |
        |                    |           Moves to: Completed tab      |
        |                    |                 [END]                  |
        |                    |                                        |
        |  Status: APPROVED  |  Sees in Approved tab                  |
        |  (Green badge)     |                                        |
        |                    |                                        |
        |            .------ DECISION ------.                         |
        |            |                      |                         |
        |         FULFILL               ON HOLD                       |
        |       (remark opt.)         (remark required)               |
        |            |                      |                         |
        |            |             Status: ON HOLD                    |
        |            |             (Orange badge)                     |
        |            |             Moves to: On Hold tab              |
        |            |                      |                         |
        |            |              [Wait for stock]                  |
        |            |                      |                         |
        |            |                  FULFILL                       |
        |            |              (remark mandatory)                |
        |            |                      |                         |
        |            '-------.   .----------'                         |
        |                    |   |                                    |
        |            Status: FULFILLED                   Asset record |
        |            (Blue badge)                        created      |
        |            Moves to: Completed tab             in ITAM      |
        |            Asset tag assigned                               |
        |                                                             |
        |  Timeline shows full audit trail                            |
        |  with dates, actors, and remarks                            |
        |  at every stage                                             |
        |                                                             |
        |--- CANCEL (only if Pending) -----> Status: CANCELLED        |
        |  (Gray badge)                      Moves to: Completed tab  |
        |                                    Removed from Pending tab |
```

---

## Scenario 13: What the System Catches -- Validation and Guardrails

The system is designed to prevent mistakes, enforce good data practices, and maintain role boundaries.

**For the Asset Requestor:** If an employee tries to submit the form without selecting a person, the system stops them with a validation message. If they type a justification that is too short -- say, just "I need one" -- the system requires at least 20 characters to ensure the request has enough context for the Manager to make a decision. The date picker prevents anyone from selecting a date in the past, so every needed-by date is always in the future. If the Requestor tries to navigate to the Manage Requests URL directly, the system blocks them -- that section is not accessible to their role.

**For the Asset Manager:** If she tries to reject a request without providing a reason, the system blocks the action and shows an error. Every rejection must come with a clear explanation. When fulfilling a request from the On Hold tab, the remark is mandatory -- the system needs a record of what resolved the hold. The Manager cannot approve, reject, or take any admin action from their My Requests view -- they must switch to the Manage Requests view to perform administrative functions, keeping the two roles clearly separated even within the same user session.

**General guardrails:** If someone searches for something that does not exist -- say, typing "printer" when there are no printer requests -- the list shows an empty state with a clear message instead of a confusing blank screen. If someone switches the person type from Employee to Consultant midway through filling out the form, the person dropdown resets and the metadata panel clears, ensuring there is no data carryover between the two different data sources.

---

## Tab Structure Summary (Asset Manager - Manage Requests)

| Tab | What It Shows | Available Actions | Badge Colors |
|-----|--------------|-------------------|--------------|
| **Pending** | New requests awaiting initial review | Approve, Reject, View | Yellow (Pending) |
| **Approved** | Approved requests ready for fulfillment | Fulfill, On Hold, View | Green (Approved) |
| **On Hold** | Approved requests blocked by stock/logistics | Fulfill, View | Orange (On Hold) |
| **Completed** | All finalized requests | View only | Blue (Fulfilled), Red (Rejected), Gray (Cancelled) |
| **All Requests** | Every request across all statuses | View only (actions via specific tabs) | All colors |

---

## Status Flow Summary

```
                    ┌──────────────────────────────────────────┐
                    |            ASSET REQUESTOR               |
                    |          submits request                  |
                    └──────────────┬───────────────────────────┘
                                   |
                                   v
                    ┌──────────────────────────────┐
                    |     PENDING (Yellow)         |
                    |     Tab: Pending             |
                    └──────┬──────────┬────────────┘
                           |          |
                   Requestor cancels  |  Manager reviews
                           |          |
                           v          |
                    ┌────────────┐    |
                    | CANCELLED  |    |
                    | (Gray)     |    |
                    | Tab:       |    |
                    | Completed  |    |
                    └────────────┘    |
                                      |
                          ┌───────────┴──────────┐
                          |                      |
                      Approve                 Reject
                          |                      |
                          v                      v
                 ┌─────────────────┐    ┌────────────┐
                 | APPROVED (Green)|    | REJECTED   |
                 | Tab: Approved   |    | (Red)      |
                 └───┬─────────┬───┘    | Tab:       |
                     |         |        | Completed  |
                  Fulfill   On Hold     └────────────┘
                     |         |
                     |         v
                     |  ┌──────────────┐
                     |  | ON HOLD      |
                     |  | (Orange)     |
                     |  | Tab: On Hold |
                     |  └──────┬───────┘
                     |         |
                     |      Fulfill
                     |   (when stock
                     |    arrives)
                     |         |
                     v         v
                 ┌──────────────────┐
                 | FULFILLED (Blue) |
                 | Tab: Completed   |
                 | Asset tag linked |
                 └──────────────────┘
```

---

## Recommended Presentation Order

For maximum impact during the client demo, present the scenarios in this order:

1. **Role Definitions** -- Start by explaining the two roles and their permissions. This frames everything that follows.
2. **Scenario 12** (Full Journey) -- Walk through the lifecycle diagram so the client sees the big picture before any live demo.
3. **Scenario 1** (Juan's Laptop Request) -- Live demo of a Requestor submitting a request. Point out that the Manage Requests section is not visible.
4. **Scenario 2** (Maria the Consultant) -- Show the Employee vs. Consultant distinction.
5. **Scenario 3** (History, Search, and Cancel) -- Demonstrate Requestor self-service and toolbar.
6. **Scenario 4** (Manager Approves) -- Switch to the Manager role. Show the Pending tab and approval workflow.
7. **Scenario 5** (Manager Rejects) -- Show rejection with mandatory reason.
8. **Scenario 6** (Fulfill from Approved Tab) -- Show the Approved tab and fulfillment action.
9. **Scenario 7** (Out of Stock - On Hold) -- Address the real-world gap between approval and fulfillment.
10. **Scenario 8** (On Hold to Fulfilled) -- Show resolution when stock arrives.
11. **Scenario 9** (Manager's Own Request) -- Demonstrate that Managers follow the same process.
12. **Scenario 11** (Completed Tab) -- Show the final-state view for reporting.
13. **Scenario 10** (Toolbar Features) -- Power-user demo of sort, group, and search.
14. **Scenario 13** (Validation & Guardrails) -- Close with confidence.

**Estimated Demo Time:** 25-30 minutes for the full walkthrough, or 12-15 minutes for a condensed version covering Scenarios 12, 1, 4, 6, 7, 8, and 11.

---

## Quick Reference

**Roles:** Asset Requestor (submit, view, cancel own) | Asset Manager (all Requestor capabilities + review, approve, reject, fulfill, hold)

**Statuses:** Pending (Yellow) > Approved (Green) > Fulfilled (Blue) | On Hold (Orange) | Rejected (Red) | Cancelled (Gray)

**Manager Tabs:** Pending | Approved | On Hold | Completed | All Requests

**Priorities:** Low (nice-to-have) | Medium (productivity) | High (significant impact) | Critical (cannot work)

**Person Types:** Employee (HR data source) | Consultant (Vendor Management data source)

**Asset Categories:** Laptop, Desktop, Monitor, Keyboard, Mouse, Memory, Storage, Printer, Headset, Webcam, Docking Station, Other
