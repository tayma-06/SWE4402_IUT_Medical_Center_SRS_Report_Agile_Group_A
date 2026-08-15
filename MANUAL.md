# IUT Medical Center Wireframe — User Manual

> [!IMPORTANT]
> ## Role selection is **demonstration only**
> The **Demo Role Switcher** exists only so the presenter can show every role from one HTML wireframe. **It will not exist in the actual system.**
>
> In the real application, the user logs in with the institutional IUT account and the system automatically identifies the authorized role and opens the correct dashboard. A student cannot switch to Doctor, a Nurse cannot switch to Finance, and so on. Role access is determined by authentication and role-based authorization.

> **Manual format:** Most workflows below use **Action → Reaction → Source → Destination** so it is clear what a button does, what changes after it is pressed, where the information came from, and where it goes next.

---

## 1. How to Open the Wireframe

### Recommended method

| Action | Reaction |
|---|---|
| Keep the `.html` wireframe file on your computer | No installation is required |
| Double-click the HTML file | It opens in the default browser |
| Or right-click → **Open with** → Chrome / Edge / Firefox | The wireframe opens as a normal local web page |
| Use **Desktop 1440** | Shows the full desktop presentation layout |
| Use **Mobile 390** | Shows the mobile presentation layout |

### Login in the prototype

1. Choose a role using **Demo Role Switcher** only for the presentation.
2. Use the prefilled demo email or another non-empty email.
3. Enter any non-empty password.
4. Press **Login**.
5. The selected demo dashboard opens.

**Actual system:** the user will enter the institutional credentials and press **Login**. The system will automatically load the dashboard assigned to that account. There will be **no role-selection combo box**.

---

## 2. Presentation Controls

| Control | Action | Reaction |
|---|---|---|
| **Demo Role Switcher** | Choose another role during presentation | Loads that role's dashboard and navigation in the prototype only. After login, the demo switcher is kept in the presentation bar only. **This control does not exist in production.** |
| **Desktop 1440** | Click | Changes the prototype frame to desktop width |
| **Mobile 390** | Click | Changes the prototype frame to mobile width |
| **Left navigation** | Click a menu item | Opens that role's corresponding workspace |
| **Search current list** | Type text | Filters visible rows in the current table |
| **Tabs / pills** | Click a tab | Opens that section without leaving the current workspace |
| **Avatar** | Click | Opens account menu |
| **View Account** | Click | Opens a read-only account popup |
| **Change Password** | Click | Opens password-change popup |
| **Logout** | Click | Returns to login screen |

### Access badges

| Badge | Meaning |
|---|---|
| **VIEW ONLY** | User can inspect data but cannot change the source record |
| **MIXED ACCESS** | User can view source data and edit only the workflow step owned by that role |
| **EDITABLE** | User owns the current workflow and can modify it |

---

## 3. Common Button Language

The wireframe uses the same words consistently across roles.

| Button / Control | Action | Reaction | Where it goes |
|---|---|---|---|
| **View Details** | Open a record | Read-only popup opens | Stays in current role |
| **View Report** | Open a published lab report | Report document preview opens | Stays in current role |
| **Download / Download Document** | Download a published lab report | Prototype downloads a report document | User's device |
| **Accept** | Approve a decision | Status changes to accepted/approved | Next workflow owner |
| **Reject** | Reject a decision | Status changes to rejected | Workflow stops or returns for correction |
| **Clarification** | Request more information | Status changes to clarification required | Previous/requesting party |
| **Status dropdown → Update Status** | Select a new process state, then update | Status is updated without opening a separate edit form | Same workflow / next stage |
| **Send to CMO** | Send prepared/updated report | Confirmation popup appears | CMO Records Inbox |
| **Forward** | CMO chooses destination and forwards | Record is marked forwarded | Selected department |
| **Dispense** | Start medicine issue | Confirmation popup appears | Pharmacy/Inventory transaction |
| **Process / Continue** | Open a lab request for processing | Opens Lab Report Processing workspace | Laboratory workflow |
| **Start Consultation** | Start clinical encounter | Opens Clinical Workspace | Doctor/CMO clinical workflow |
| **View Profile** | Open patient history | Patient profile popup appears | Read-only patient context |

---

# 4. Roles at a Glance

| Role | Main responsibility |
|---|---|
| **Student / Patient** | View own health record and submit requests/claims |
| **Faculty / Staff** | View own/dependent health records and submit requests/claims |
| **Doctor / Medical Officer** | Consultation, prescription, lab/diagnostic requests, referral, certificates, emergency decisions |
| **Nurse / Medical Attendant** | Vitals, procedures, daily care, emergency triage, ambulance request, observation beds, dispensing, stock, reports |
| **Laboratory Technician** | Receive lab requests, process samples, enter/verify/publish downloadable lab reports |
| **CMO** | Clinical oversight, staff scheduling, approvals, report routing, emergency escalation |
| **Registrar** | Emergency exam decision/scheduling and staff absence coordination |
| **Ambulance Driver** | Accept ambulance requests and share live trip status/location |
| **Accounts / Finance / Cashier** | Payouts, referral payments, external hospital bills, refunds, audit view |
| **Procurement / Authorized Admin / VC** | Receive approved needs and update procurement/tender/delivery stages |
| **Public On-Duty Board** | View duty/on-call/hotline information only |

---

# 5. Student / Patient Manual

## Dashboard

**Action:** Open **Dashboard**.  
**Reaction:** Shows summary cards and current items.  
**Source:** Patient record, prescription, lab, certificate/request statuses.  
**Destination:** None — summary only.

## My Health

### Medical Record

**Action:** Open **My Health → Medical Record**.  
**Reaction:** Shows demographic/clinical information and recent visits.  
**Source:** Unified patient record.  
**Destination:** Read-only.

### Vitals History

**Action:** Press **Vitals History**.  
**Reaction:** Shows BP, pulse, temperature, weight and RBS history.  
**Source:** Nurse / Medical Attendant vital records.  
**Destination:** Read-only patient view.

### Prescriptions

**Action:** Press **Prescriptions**.  
**Reaction:** Shows finalized prescriptions and dispensing state.  
**Source:** Doctor prescription + Nurse dispensing status.  
**Destination:** Read-only patient view.

### Lab & Diagnostic Results

**Action:** Press **Lab & Diagnostic Results**.  
**Reaction:** Shows laboratory and diagnostic results in one list.

- **View Report** → opens a published laboratory document.
- **Download** → downloads the published report document.
- A lab request that is still **Processing** has no downloadable report yet.
- **View Details** on a diagnostic result opens its record details.

**Source:** Laboratory publication / diagnostic service result.  
**Destination:** Patient medical record.

### Referrals

**Action:** Press **Referrals**.  
**Reaction:** Shows finalized referral history.  
**Source:** Doctor referral.  
**Destination:** Read-only patient view.

## Requests & Claims

### Medical Certificate

**Action:** Fill the certificate form and supporting document.  
**Reaction:** Request becomes a medical certificate request.  
**Goes to:** Doctor review.  
**After doctor decision:** Request becomes Approved / Rejected / Clarification Required; issued certificate is shown when available.

### Emergency Exam — Student only

**Action:** Fill exam/course, exam date, medical reason and supporting document.  
**Reaction:** Emergency exam request is created.  
**Flow:** Student → Doctor medical assessment → Registrar review → CMO if required → Approved/Rejected → Scheduling.

### Reimbursement Claim

**Action:** Enter Bank A/C, reference/prescription code, expense document serials, amounts and proofs.  
**Reaction:** **TOTAL** updates automatically whenever an amount changes.  
**Action:** Press **Submit Claim with Proofs**.  
**Intended reaction:** Claim is submitted for validation and CMO medical review.  
**Flow:** Student claim → CMO review → if approved → Finance payout queue → payment status shown to student.

The reimbursement expense groups are:

1. Consultation fees
2. Medicines
3. Laboratory / Clinical Test
4. Hospital / Clinic bills

Each expense group has its own **Payment Document Serials**, **Taka**, and **Proof** field.

## Notifications

**Action:** Open **Notifications**.  
**Reaction:** Shows updates such as lab processing or dispensing changes.  
**Source:** Other connected workflows.  
**Destination:** Read-only notification feed.

---

# 6. Faculty / Staff Manual

Faculty/Staff uses the same health and request structure as Student, but the identity model is separate.

> **Example:** Faculty ID uses a faculty format such as `FAC-00127`; a dependent uses a separate dependent ID. Student IUT IDs are not reused for faculty identity.

## My & Dependents Health

**Action:** Change **Currently Viewing**.  
**Reaction:** Health tabs switch to the selected faculty member or dependent.  
**Source:** Faculty account + linked dependent record.  
**Destination:** All health tabs below use the selected patient context.

Available tabs:

- Medical Record
- Vitals History
- Prescriptions
- Lab & Diagnostic Results
- Referrals

Published laboratory reports can be **viewed and downloaded** exactly like the Student role.

## Requests & Claims

### Medical Certificate

**Action:** Select **My Profile** or a dependent, enter certificate details, upload proof.  
**Reaction:** Request is created for the selected person.  
**Goes to:** Doctor review.

### Reimbursement

**Action:** Submit the expense form.  
**Reaction:** Claim total calculates automatically.  
**Goes to:** CMO medical review → Finance if approved.

> Faculty does not use the Student Emergency Exam tab in this wireframe.

---

# 7. Doctor / Medical Officer Manual

## Dashboard

**Action:** Open **Dashboard**.  
**Reaction:** Shows patient load, consultations, lab results and pending certificate work.  
**Purpose:** Summary only.

## Patient Search

### View Profile

**Action:** Search by IUT ID/name/category → press **View Profile**.  
**Reaction:** Popup shows patient identity, latest vitals, previous consultation, prescriptions, lab/diagnostic results, referrals and emergency history.  
**Source:** Unified patient record.

### Start Consultation

**Action:** Press **Start Consultation**.  
**Reaction:** Opens **Clinical Workspace** for the selected patient.  
**Data carried forward:** Identity, allergies, previous visits, latest vitals, active prescription, lab/diagnostic results, referral history and emergency history.

## Clinical Workspace

### Consultation + Prescription

**Action:** Enter complaint, duration, examination findings, investigation, advice and follow-up.  
**Reaction:** Consultation record is prepared.

**Action:** Edit medication, dosage, frequency, duration or instructions.  
**Reaction:** The **Prescription Record Preview updates live**.  
**Goes to after finalization:** Nurse / Medical Attendant dispensing queue.  
**Then:** Dispensing updates medicine inventory.

### Lab & Diagnostics

#### Laboratory Request

**Action:** Select test + priority + clinical note.  
**Reaction:** Formal lab request is created.  
**Flow:** Doctor → Lab Request Queue → Sample/Processing → Verification → Publication → Patient/Doctor record.

#### Diagnostic Request

**Action:** Select X-ray / ECG / Ultrasound and priority.  
**Reaction:** Diagnostic request starts.  
**Flow:** Request → Availability → Booking/Payment → Service → Result.

### Referral

**Action:** Select specialist type and enter referral reason.  
**Reaction:** Referral record is prepared using patient data already in the system.  
**Flow:** Doctor referral → referral/payment process if applicable → receiving provider / patient record.

### Medical Certificate

**Action:** Select certificate request → press **Accept** or **Reject**.  
**Reaction:** Decision status changes.  
**Source:** Student/Faculty certificate request.  
**Destination:** Requester receives the resulting status/certificate.

### Emergency Exam

**Action:** Enter medical findings and recommendation.  
**Reaction:** Doctor medical assessment is recorded.  
**Goes to:** Registrar.  
**Important:** Registrar owns the academic approval and scheduling; Doctor owns only medical assessment.

## Emergency

### Active Emergency Cases

**Action:** Open **Active Emergency Cases**.  
**Reaction:** Shows cases already registered/triaged by Nurse / Medical Attendant.

### Clinical Decision

**Action:** Open **Clinical Decision**.  
**Reaction:** Doctor sees identity, alerts, prior medical information, latest vitals, triage, emergency procedures and transfer context together.

**Action:** Choose decision:

- Treat On-site
- Bed Rest / Observation
- Emergency Referral
- Ambulance Transfer
- Discharge After Stabilization

**Reaction:** The next emergency step follows the selected decision.

### Ambulance Transfer

**Action:** Doctor or Nurse creates the ambulance request.  
**Reaction:** Request appears in **Ambulance Driver → Ambulance Requests**.  
**Driver presses Accept:** Driver response becomes accepted and live tracking begins.  
**Doctor/Nurse reaction:** Map panel shows driver/vehicle, current location, last update and ETA.

---

# 8. Nurse / Medical Attendant Manual

## Dashboard

**Action:** Open **Dashboard**.  
**Reaction:** Shows prescription queue, stock warnings, waiting vitals and expiry alerts.

## Patient Search

**Action:** Search patient.  
**Reaction:** Returns matching patient records.  
**Source:** Unified patient record.  
**Destination:** Nurse-owned care workflows.

## Patient Care

### Routine Vitals

**Action:** Enter BP, pulse, temperature, weight, RBS and note.  
**Reaction:** One reusable vital record is created.  
**Used by:** Routine consultation and Emergency Triage.  
**Important:** Emergency does not duplicate the same vitals.

### Procedures

**Action:** Select Dressing / Injection / Oxygen / Nebulization / Other Treatment and record details/outcome.  
**Reaction:** Procedure record is created under the patient.  
**Source instruction:** Prescription / clinical order where applicable.

### Daily Tracking

**Action:** Select care item and care status.  
**Reaction:** Daily follow-up is recorded.  
**Important:** Daily tracking does **not** deduct pharmacy stock; dispensing does that.

### Emergency Case

**Action:** Open **Emergency Case**.  
**Reaction:** Existing patient alerts, latest linked vitals and prior records are shown immediately.

#### Emergency Triage

**Action:** Choose triage level, risk, presenting emergency, assessment and next action.  
**Reaction:** Triage severity and assessment are stored against the emergency case.  
**Goes to:** Doctor Emergency workspace when doctor review is required.

#### Emergency Procedure Record

**Action:** Record emergency procedure, details, patient response, current state and escalation.  
**Reaction:** Emergency procedure record is stored separately from triage.

#### Call Ambulance

**Action:** Complete Request ID, case, requested by, reason, destination, priority and handover note → press **Call Ambulance**.  
**Intended reaction:** Request is sent directly to the **Ambulance Driver queue**.  
**Driver Accepts:** Nurse sees acceptance, current trip status, live location, last update and ETA in the map/request tracking area.

#### Emergency Ambulance Requests

**Action:** Press **View Details** on a request.  
**Reaction:** Transfer request details open.  
**Source:** Doctor/Nurse ambulance call.  
**Status shown:** Awaiting Driver / Accepted / En route / Completed.

### Bed Rest / Observation

There are **6 observation beds**.

**Action:** Choose Free / Reserved / Occupied / Cleaning → press **Update Status**.  
**Reaction:** Bed state is updated.  
**Source:** Emergency/clinical decision.  
**Destination:** Shared observation-bed availability.

## Pharmacy & Inventory

### Dispensing

**Action:** Review prescription, available stock, batch and expiry → enter dispense quantity → press **Dispense**.  
**Reaction:** Confirmation popup opens.  
**Action:** Press **Confirm Dispense**.  
**Intended reaction:** Dispensing transaction is recorded and inventory decreases accordingly.

### Medicine Stock

**Action:** Search/filter medicine.  
**Reaction:** Shows batch, received, dispensed, remaining quantity, expiry and stock state.  
**Source:** Inventory ledger.

### Stock Count

**Action:** Enter Physical Qty → press **Record Count**.  
**Reaction:** Physical count/variance is recorded.  
**Source:** Recorded inventory vs physical stock.

### Stock & Expiry Alerts

**Action:** Open tab.  
**Reaction:** Shows low stock, out-of-stock and near-expiry items.  
**Source:** Inventory thresholds and expiry dates.

## Records & Reports

The Nurse / Medical Attendant can view:

- Daily Medicine Stock
- Monthly Medicine Bill
- Emergency Procedure Record
- Dressing Procedure Record
- Referral Record
- Prescription Record
- Lab Reports

### View a record

**Action:** Press **View Details**.  
**Reaction:** Read-only structured record popup opens.

### Lab Reports

**Action:** Press **View Report**.  
**Reaction:** Published lab document opens.  
**Action:** Press **Download**.  
**Reaction:** Published report is downloaded.

### Send to CMO

**Action:** Select record/report + reference + review status + update note → press **Send to CMO**.  
**Reaction:** Confirmation popup appears.  
**Goes to:** **CMO → Approvals & Records → Records Inbox**.

---

# 9. Laboratory Technician Manual

## Dashboard

**Action:** Open Dashboard.  
**Reaction:** Shows pending requests, processing, reports awaiting verification and publications.

## Lab Requests

### View Details

**Action:** Press **View Details**.  
**Reaction:** Doctor-issued lab request opens read-only.  
**Important:** Lab cannot alter the doctor's original order.

### Receive

**Action:** Press **Receive**.  
**Intended reaction:** Request state becomes Received and becomes available for processing.

### Process / Continue

**Action:** Press **Process** or **Continue**.  
**Reaction:** Opens **Report Processing** workspace.

## Report Processing

### Sample & Processing

**Action:** Enter specimen, collection time, method, processing status and note.  
**Reaction:** Lab-owned processing state is updated.

### Report Entry & Submit

**Action:** Enter findings, unit, reference range, abnormal/critical flag and/or upload digital report.  
**Reaction:** Report draft is prepared.

**Action:** Press **Save Draft**.  
**Intended reaction:** Saves unfinished result without publishing.

**Action:** Press **Submit Report**.  
**Intended reaction:** Report moves to verification; it is not yet visible as a final patient document.

### Verify & Publish

**Action:** Choose **Verified** or **Return for Correction**.  
**Action:** Press **Verify & Publish** after verification.  
**Intended reaction:** Final report is published into the unified patient record.  
**Visible to:** Treating doctor + permitted patient/faculty view + authorized Nurse/Medical Attendant record view.

### Exceptions

**Action:** Record equipment malfunction / invalid specimen / insufficient specimen / other.  
**Reaction:** No false report is published.  
**Next action:** Recollect / Retry / Notify Doctor / Escalate.

## Published Reports

**Action:** Press **View Report**.  
**Reaction:** Final document preview opens.

**Action:** Press **Download Document**.  
**Reaction:** Wireframe downloads a demonstration report file.

**Rule:** Only verified/published reports are downloadable.

---

# 10. CMO Manual

## Overview

**Action:** Open **Overview**.  
**Reaction:** Shows staffing and approval summaries.  
**Purpose:** Management overview only.

## Patient Search / Clinical Workspace

CMO can open the patient profile and clinical workspace for authorized clinical access, using the same consolidated patient history concept as the Doctor.

## Staff & Scheduling

### Duty Roster

**Action:** Select week, shift, doctor and nurse/medical attendant.  
**Reaction:** Roster is prepared/updated.  
**Validation:** Overlap, coverage and availability checks are displayed.

### Night On-Call

**Action:** Update night coverage.  
**Reaction:** On-call schedule changes.  
**Public effect:** Approved duty/on-call information can feed the Public On-Duty Board.

### Shift Changes

**Action:** Review shift change.  
**Reaction:** CMO resolves the staffing decision while maintaining coverage.

### Coverage Gaps

**Action:** Review missing role/gap.  
**Reaction:** Replacement/coverage resolution can be recorded.

### Absence

**Source:** Registrar records staff absence.  
**CMO action:** Assign replacement / coverage note.  
**Reaction:** Roster is updated.

### Emergency Exam Oversight

**Action:** Review an escalated exam case if CMO input is required.  
**Reaction:** CMO oversight status is updated; Registrar still owns final academic processing.

## Approvals & Records

### Reimbursement Review

**Source:** Student/Faculty reimbursement claim.  
**Action:** Press **View Details** → inspect claim.  
**Action:** **Accept** → claim becomes approved.  
**Goes to:** Finance → Approved Payouts.  
**Action:** **Reject** → claim stops from progressing to payment.

### External Referral Bill Review

**Source:** Finance/internal intake of an external hospital bill linked to an original referral.  
**Action:** Accept or Reject.  
**Accept reaction:** Bill becomes eligible for Finance payout.  
**Reject reaction:** Payment is blocked.

### Records Inbox

**Source:** Nurse / Medical Attendant **Send to CMO**.  
**Action:** Press **View Details**.  
**Reaction:** Record/report opens.

**Action:** Choose **Route To** department + status → press **Forward**.  
**Reaction:** Record is marked forwarded.  
**Possible destinations:** Procurement / Accounts / Medical Center Admin / Registrar depending on record.

### Procurement Need

**Source:** Low stock / medical need.  
**Action:** **Accept**.  
**Reaction:** Medical need is approved.  
**Goes to:** Procurement Workspace.  
**Reject:** Procurement flow does not proceed.

## Emergency Oversight

**Source:** Emergency case / doctor escalation.  
**Action:** Choose CMO decision such as alternative hospital / doctor review / no further action.  
**Reaction:** Oversight decision is recorded.  
**Important:** CMO does not duplicate nurse triage or doctor emergency record.

---

# 11. Registrar Manual

## Emergency Exam

### Requests

**Source:** Student request + Doctor medical assessment.  
**Action:** **View Details** to inspect request.  
**Action:** **Accept** → Approved.  
**Action:** **Reject** → Rejected.  
**Action:** **Clarification** → Clarification Required.

### Scheduling

**Action:** Enter venue, date, time and invigilator for an approved request.  
**Reaction:** Emergency exam arrangement is scheduled.

## Absence & Scheduling

### Absence Records

**Action:** Record staff, role, date and reason.  
**Reaction:** Staff absence is recorded.  
**Goes to:** CMO for clinical coverage/replacement decision.

### Schedule Coordination

**Action:** Update coordination status.  
**Reaction:** Registrar tracks exam/CMO coordination items.

---

# 12. Ambulance Driver Manual

## Dashboard

**Action:** Open Dashboard.  
**Reaction:** Shows pending ambulance calls, accepted trip, live status and completed trips.

## Ambulance Requests

**Source:** Doctor on duty or Nurse / Medical Attendant.

**Action:** Press **View Details**.  
**Reaction:** Shows transfer request, source case, requester and transfer information.

**Action:** Press **Accept**.  
**Reaction:** Request status becomes Driver Accepted.  
**Goes back to:** Doctor/Nurse request tracking.  
**Next:** Live location/status becomes available to the calling clinical staff.

**Action:** Press **Reject**.  
**Reaction:** Request shows Driver Unable / rejected state.  
**Goes back to:** Calling doctor/nurse so an alternative can be arranged.

## Live Status

**Action:** Enter current location, status and ETA/live note.  
**Action:** Press **Share Live Update**.  
**Intended reaction:** Latest driver location/status is shared with the calling Doctor/Nurse.  
**Doctor/Nurse view:** Map-based location + ETA + last update + driver/vehicle.

Possible trip states include:

- Accepted
- En route
- Arrived at Pickup
- Patient Onboard
- Arrived at Hospital
- Completed

## Transfer History

**Action:** Open history.  
**Reaction:** Shows completed transfers linked to their original emergency/night case.  
**Access:** View only.

---

# 13. Accounts / Finance / Cashier Manual

The Finance Workspace is separated by **why money is moving**.

## Approved Payouts — Money OUT

**Source:** CMO-approved Student reimbursement or CMO-approved external hospital claim.

**Action:** Open reference with **View Details**.  
**Reaction:** Claim details open.

**Action:** Choose Ready for Payment / Processing / Paid / Failed → **Update Status**.  
**Reaction:** Payment progress is updated.  
**Goes to:** Student claim status or external hospital payment record.

## Referral Counter Payment — Money IN

**Source:** Referral that requires upfront payment.

**Action:** Update Pending / Paid / Failed.  
**Reaction:** Referral payment state changes.  
**When Paid:** Receipt/reference is associated with the referral and the referral can continue.

> This is **not** reimbursement and **not** an external hospital claim.

## External Hospital Bills

**Source:** External provider bill + original referral + supporting documents entered through an authorized internal channel.

**Action:** Verify processing status.  
**Reaction:** Verified item awaits CMO review.  
**CMO Accepts:** It appears in Approved Payouts.  
**CMO Rejects:** It does not proceed to payment.

## Refunds — Money BACK

**Source:** Original referral payment.

**Action:** Update Pending / Processing / Refunded / Failed.  
**Reaction:** Refund state changes.  
**Rule:** Refund must remain linked to the original referral payment; it is not a new reimbursement claim.

## Audit Trail

**Action:** Open Audit Trail.  
**Reaction:** Shows financial actions and results.  
**Access:** Read-only / immutable in normal operations.

---

# 14. Procurement / Authorized Admin / VC Manual

## Received Requests

**Source:** CMO-approved medical need.

**Action:** Press **View Details**.  
**Reaction:** Procurement request opens.

**Action:** Choose Received / Under Administrative Review / Approved for Tender / Rejected → **Update Status**.  
**Reaction:** Procurement request moves to the selected stage.

## Tender / Vendor

**Source:** Request approved for tender.

**Action:** Update Open / Evaluation / Vendor Selected / Closed.  
**Reaction:** Tender stage changes.

## Delivery

**Source:** Selected vendor / tender result.

**Action:** Update Partial Delivery / Received / Accepted / Returned.  
**Reaction:** Delivery state changes.  
**If accepted:** Accepted quantities can feed/update medicine inventory.

## History

**Action:** Open History.  
**Reaction:** Shows completed procurement chain.  
**Access:** View only.

---

# 15. Public On-Duty Board Manual

No login-sensitive patient data is shown here.

**Action:** Open **On-Duty Board**.  
**Reaction:** Shows current doctor, nurse/medical attendant, shift time, on-call and hotline information only.

**Source:** Published duty/on-call schedule.  
**Destination:** Public read-only view.

**Never shown publicly:**

- Patient identity
- Diagnosis
- Prescription
- Lab report
- Referral
- Financial/claim information

---

# 16. Main End-to-End Connections

## A. Consultation → Prescription → Dispensing → Inventory

**Doctor starts consultation**  
→ creates/finalizes prescription  
→ prescription appears for Nurse/Medical Attendant  
→ Nurse presses **Dispense** and confirms  
→ dispensing record is created  
→ inventory quantity decreases  
→ patient sees dispensing status.

## B. Doctor Lab Request → Published Downloadable Report

**Doctor creates Laboratory Request**  
→ Lab Request Queue  
→ Lab processes sample  
→ Lab enters report  
→ report submitted  
→ report verified  
→ **Verify & Publish**  
→ final report enters patient record  
→ Doctor / Patient / authorized Nurse can **View Report** and **Download**.

## C. Emergency → Ambulance → Live Map

**Nurse triages emergency**  
→ Doctor reviews clinical case when required  
→ Doctor or Nurse presses/initiates **Call Ambulance**  
→ request reaches Ambulance Driver  
→ Driver presses **Accept**  
→ clinical staff sees accepted status  
→ Driver shares live update  
→ Doctor/Nurse sees map, current location, last update and ETA  
→ trip becomes Completed  
→ record moves to Transfer History.

## D. Reimbursement → CMO → Finance

**Student/Faculty submits itemized claim + proofs**  
→ total calculates automatically  
→ CMO opens claim  
→ CMO **Accepts** or **Rejects**  
→ Accepted claim goes to Finance Approved Payouts  
→ Finance updates payment status  
→ claimant sees final payment state.

## E. Nurse Report → CMO → Department

**Nurse prepares/updates report**  
→ presses **Send to CMO**  
→ CMO Records Inbox  
→ CMO opens record  
→ selects Route To  
→ presses **Forward**  
→ selected department receives the information.

## F. Low Stock → CMO → Procurement → Delivery → Inventory

**Inventory shows low stock**  
→ medical need prepared  
→ CMO approves need  
→ Procurement receives request  
→ tender/vendor stage updated  
→ delivery received/accepted  
→ accepted quantity can update medicine inventory.

## G. Emergency Exam

**Student submits Emergency Exam Request**  
→ Doctor records medical recommendation  
→ Registrar reviews  
→ CMO only if required  
→ Registrar Accepts / Rejects / Clarification  
→ if accepted, Registrar schedules venue/date/time/invigilator.

---

# 17. Prototype vs Final System

This file is a **wireframe/prototype**, so it demonstrates navigation, ownership, information structure and selected interactions rather than implementing a production database.

### Working prototype interactions include

- Role switching for presentation
- Desktop / Mobile preview
- Navigation and tabs
- Search/filter of visible table rows
- View Details popups
- Patient profile popup
- Start Consultation navigation
- Lab Process / Continue navigation
- Published Lab Report view/download
- Claim total auto-calculation
- Accept/Reject status reaction
- Status dropdown + Update Status feedback
- Send to CMO confirmation
- Dispensing confirmation popup

### Presentation-only / intended production actions

Some buttons show the intended system operation but do not persist data in a backend database in this static HTML prototype, including actions such as final form submission, saving to a real database, true GPS tracking, payment API execution and real institutional authentication.

---

## Quick Presentation Tip

For a clean demonstration, present one complete flow at a time:

**Student → Doctor → Nurse → Lab → CMO → Finance/Procurement → Ambulance Driver**, switching roles only to demonstrate the handoff.

In the production system, these handoffs happen between **different authenticated users**. The presenter changes roles only through the **Demo Role Switcher** to demonstrate those handoffs; production users never switch roles manually.
