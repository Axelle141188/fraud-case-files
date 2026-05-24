# Fraud Case File #03 — Internal Fraud at CCF: The Valdy Case

**Type:** Internal Fraud / Insider Threat / Identity Theft / Organized Fraud  
**Country:** France  
**Year:** 2025  
**Amount:** ~€400,000  
**Victims:** 11 clients of the Platine branch, Paris 7th arrondissement  
**Sources:** Le Parisien, Le Tribunal du Net

---

## 1. Case Summary

In just a few months, a temporary worker assigned to the Platine branch of CCF on Rue de Grenelle in Paris diverted nearly €400,000 — without ever forcing a single lock.

Valdy, a temporary employee, exploited the legitimate access her position granted her to modify the personal data of 11 clients, order new bank cards without their knowledge, increase their payment limits, and arrange transfers to fictitious companies. She operated with a network of accomplices spread across several French cities. By the time management discovered the fraud, Valdy had already boarded a flight to Congo. The affected clients were fully reimbursed by the bank.

---

## 2. Attack Flow

**Step 1 — Legitimate Access**  
As a temporary employee, Valdy was granted access to the branch's internal systems. This access, necessary for her day-to-day functions, allowed her to view and modify client personal data.

**Step 2 — Modifying Client Data**  
Valdy altered the personal information on 11 client accounts — phone numbers, addresses — to intercept banking notifications intended for the real account holders. Clients stopped receiving transaction alerts on their own devices.

**Step 3 — Ordering New Cards**  
Using the modified data, she ordered new bank cards in the clients' names. These cards were sent to or collected by herself or her accomplices.

**Step 4 — Increasing Payment Limits**  
She raised the payment limits on targeted accounts to maximize the amounts that could be withdrawn without triggering automatic alerts.

**Step 5 — Transfers and Withdrawals**  
Funds were withdrawn as cash or transferred to fictitious companies. The accomplice network operated from several cities — Joué-lès-Tours, Évry, Bry-sur-Marne, Melun — and included at least one individual operating from inside Orléans prison.

**Step 6 — Flight**  
Before management even filed a complaint, Valdy boarded a flight to Congo. Her anticipatory flight indicates a clear awareness of when the fraud would be discovered.

---

## 3. Psychological Techniques

In this case, the psychological manipulation does not target the direct victims — it targets the institution itself.

**Exploitation of Institutional Trust**  
Valdy held legitimate system access. In a banking environment, employees — even temporary ones — are assumed trustworthy by default. This automatic institutional trust was the first vulnerability exploited.

**Opportunistic Insider Profile**  
Insider threats do not always look the way we expect. Not necessarily a disgruntled employee or someone visibly struggling financially. Sometimes it is someone who identifies an opportunity, assesses the risks, and acts methodically.

**Lack of Affective Commitment**  
A temporary worker with no long-term career prospects within the organization does not develop the same emotional bond as a permanent employee. This absence of affective commitment significantly lowers the psychological barrier against fraud — loyalty to the institution is not a deterrent. The organized flight before discovery suggests that the exit strategy was part of the plan from the start.

**Invisibility Through Status**  
The temporary worker status plays a paradoxical role: perceived as transient and therefore low-risk, Valdy was likely subject to less scrutiny than a permanent employee. The social invisibility of temporary workers becomes a tactical advantage.

**Fragmentation of Actions**  
Each individual action — modifying a phone number, ordering a card, raising a limit — appears routine in isolation. It is their combination that constitutes the fraud. This fragmentation makes real-time detection extremely difficult.

---

## 4. Technical Indicators

- Repeated modifications to client Master Data across multiple accounts in a short timeframe — a behavioral deviation detectable by a UEBA tool
- New bank cards ordered without explicit requests from account holders
- Unsolicited payment limit increases across multiple accounts simultaneously
- Transfers directed toward newly added beneficiaries with no prior relationship history
- Real account holders no longer receiving alerts due to modified contact data

---

## 5. Detection Opportunities

**UEBA (User and Entity Behavior Analytics):** A behavioral monitoring tool should have flagged the deviation in Valdy's user account — a temporary employee consulting and modifying Master Data across 11 client accounts in a short period represents a clear behavioral anomaly relative to her standard role profile.

**Master Data Change Monitoring:** Any modification to a client's phone number or address should have triggered an independent verification with the account holder — via their previous contact details or by post.

**Card Order Alerts:** A new card order not initiated by the client through their own channels should have generated a direct confirmation request to the account holder.

**Action Correlation:** Linking multiple sensitive actions on the same account within a short timeframe would have revealed the pattern well before the damage reached €400,000.

---

## 6. Prevention

**Principle of Least Privilege:** Restrict temporary employees' system access to the strict minimum required for their role — a temporary worker does not need full access to all client data.

**Four-Eyes Principle and Segregation of Duties (SoD):** No single individual should be able to modify client data, order a card, and raise a payment limit without validation from a second employee. This fundamental banking security principle would have blocked the fraud at Step 2.

**UEBA Deployment:** Monitor internal user behavior in real time, with particular attention to accounts held by users with temporary access rights.

**Automatic Client Alerts:** Any change to personal data should trigger an immediate notification to the account holder through their previous contact channels.

**Manager Training:** Equip managers to recognize behavioral signals of an insider threat, particularly among short-term or temporary staff profiles.

---

## 7. Lessons Learned

> *"The threat does not always come from outside. Sometimes, it walks in with a badge and a smile."*

The Valdy case serves as an uncomfortable reminder for financial institutions: the security perimeter does not end at the branch door. Poorly supervised legitimate access is a vulnerability — whether held by a permanent employee or a temporary worker.

For any fraud analyst, this case illustrates the critical importance of internal behavioral monitoring and UEBA: it is not isolated actions that reveal fraud, it is their pattern. Connecting weak signals — a data modification here, a card order there, a limit increase elsewhere — is precisely what distinguishes a strong analyst from a simple rule checker.
