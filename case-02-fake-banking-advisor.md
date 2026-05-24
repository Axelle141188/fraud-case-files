# Fraud Case File #02 — Fake Banking Advisor Network

**Type:** Social Engineering / APP Fraud (Authorized Push Payment Fraud) / Identity Impersonation / Organized Fraud  
**Country:** France  
**Period:** April 2022 — April 2023  
**Amount:** €740,000  
**Victims:** ~100 individuals across France  
**Sources:** Le Parisien, Génération NT, Banque de France

---

## 1. Case Summary

Between April 2022 and April 2023, an organized network of eleven individuals orchestrated a wave of banking fraud targeting ordinary citizens across France. Their weapon of choice: no malware, no sophisticated hacking. Just a text message, a phone call, and carefully crafted psychological manipulation.

By impersonating legitimate bank advisors, the fraudsters convinced their victims to authorize fraudulent transfers themselves — a scheme known as **APP Fraud (Authorized Push Payment Fraud)**: the victim authorizes the payment, believing they are acting in their own best interest. Total damage: €740,000. Trial opened before the Paris Criminal Court in March 2026.

---

## 2. Attack Flow

**Step 1 — The Alarm Text**  
The victim receives a text message appearing to come from their bank. The message warns of a suspicious transaction or fraud attempt on their account and urges them to call an emergency number immediately.

This SMS appears in the same conversation thread as genuine bank messages through **sender name spoofing**: fraudsters impersonate the bank's display name (e.g. "MyBank") in the SMS. The SMS protocol does not verify whether the sender is legitimate — anyone can send a message under the name "MyBank". As a result, the fraudulent SMS appears alongside real bank messages in the victim's inbox, making visual detection virtually impossible. This protocol dates back to the 1970s and was never designed to authenticate senders — a well-known vulnerability that remains widely exploited today.

**Step 2 — The Fake Advisor Calls**  
The victim calls back. A professional, calm, and reassuring voice answers. The caller introduces themselves as an advisor from the bank's anti-fraud department. They sometimes know the victim's first name, their bank's name, or even an approximate account balance — information obtained through stolen databases or dark web purchases.

**Step 3 — Building Trust**  
The fake advisor explains that a fraud attempt is currently underway on the victim's account. They come across as reassuring, competent, and appropriately urgent. They guide the victim step by step through the process of "securing" their account.

**Step 4 — Authorizing the Transfer**  
Under the pretense of security, the fake advisor asks the victim to validate one or more transfers to a "temporary secure account." The victim, convinced they are acting to protect themselves, authorizes the transactions — this is precisely the APP Fraud mechanism at work.

**Step 5 — Disappearance and Money Laundering**  
Funds are immediately dispersed across multiple relay accounts, withdrawn as cash, or converted. The network operated from several cities across France — including one accomplice operating from inside Orléans prison.

---

## 3. Psychological Techniques

This is the core of the case. No technical vulnerability was exploited — only human ones.

**Artificial Urgency**  
The initial text message immediately triggers a stress response. The victim believes their money is at risk right now. Under acute stress, the brain prioritizes fast action over critical thinking — exactly what the fraudsters needed.

**Authority Impersonation**  
The fake advisor embodies a figure of legitimate authority — the bank, a trusted institution. Milgram's obedience principle applies directly: when faced with a perceived authority figure, individuals tend to comply without questioning.

**Illusion of Control**  
This is the central mechanism of APP Fraud. The fake advisor does not make the transfers on the victim's behalf — they ask the victim to do it themselves. Psychologicaly, being the one who clicks ("I'm securing my own account") creates a false sense of control over the situation. This illusion of control dismantles the victim's last line of defense against suspicion.

**Consistency Principle**  
Once the victim has started following instructions, they keep going. Admitting mid-way through that you are being manipulated is psychologically uncomfortable — it is easier to see it through so the situation "makes sense."

**Informational Isolation**  
The fake advisor often asks the victim not to mention this to anyone immediately, "to avoid compromising the ongoing investigation." Cutting the victim off from their support network means cutting them off from the people most likely to help them realize something is wrong.

**False Reciprocity**  
The advisor presents themselves as someone who is helping, protecting. The victim feels cooperative and grateful — they want to "do their part" to resolve the situation together.

---

## 4. Technical Indicators

This case is primarily human in nature, but technical signals were present:

- Sender name spoofing: the bank's display name was impersonated, making visual verification impossible for the victim
- Fraudulent SMS integrated into the victim's genuine bank message thread
- Transfers directed toward recently opened relay accounts, often abroad
- Multiple transactions in rapid succession on victim accounts
- Inbound calls not initiated by the bank, immediately followed by unusual outgoing transfers

---

## 5. Detection Opportunities

**On the bank's side:**
- Behavioral detection: an unusual transfer validated shortly after an unsolicited inbound call should have triggered an automatic alert
- Independent verification callback: contacting the client on their registered number before validating any unusual transfer
- The PSD2 directive (Payment Services Directive 2) mandates Strong Customer Authentication (SCA) — but in APP Fraud, it is precisely the victim who authenticates themselves, effectively bypassing the technical protection. This is the fundamental limitation of SCA against social manipulation.
- Since October 2024, the Naegelen Law in France prohibits the spoofing of bank phone numbers — making this type of fraud significantly harder to execute technically

**On the victim's side:**
- Always call the bank back using the number on the back of your bank card — never a number provided in a text message
- Never authorize a transfer under phone pressure, even from someone who appears legitimate
- A real bank will never ask you to validate a transfer in order to "secure" your account

---

## 6. Prevention

- Public awareness campaigns on sender spoofing and APP Fraud
- Training bank employees to detect suspicious client behavior during payment validation
- Implementation of security delays on unusual transfers
- Strict enforcement of the Naegelen Law and anti-spoofing mechanisms
- Anticipating PSD3: strengthening bank reimbursement obligations in APP Fraud cases
- Encouraging victims to report immediately via cybermalveillance.gouv.fr

---

## 7. Lessons Learned

> *"Social engineering fraud does not exploit your computer. It exploits your trust — and your need for control."*

This case illustrates a fundamental truth: the most sophisticated security systems offer no protection against human manipulation. The network needed no malware, no hacking — just a text message and a convincing voice.

For any fraud analyst, this case underscores the critical importance of behavioral detection: it is not the transaction itself that is anomalous — it is the context in which it is initiated. And when it comes to APP Fraud, the real line of defense is not technical. It is human.
