Assignment: Voice Agent Design

1. Usecase: Home Credit Loan Against Property (LAP) Qualification
Our goal is to deploy an automated AI Voice Agent for “Home Credit” to
contact our existing,
valued customers. The agent's primary purpose is to inform them of a
pre-approved Loan Against Property (LAP) offer and conduct a preliminary
eligibility check.
The conversation must feel natural, professional, and advisory. The agent acts
as the first point of contact to "qualify" the lead before we transition them to
a senior human loan expert to finalize the application.

2. Call Interaction Usecase
The agent must successfully navigate through the following stages during the
call:
A. Greeting and Identification
Verify that you are speaking with the correct customer. If the customer is busy,
acknowledge this and ask for a preferred callback time.
B. Presenting the Offer
Once verified, explain the reason for the call: rewarding the customer’s loyalty
with a special Loan Against Property offer of up to 75,00,000 (75 Lakhs).
C. The Eligibility Checklist & Criteria
The core of this usecase is gathering 7 specific data points to determine if the
customer qualifies for the loan. The bot must capture these details
sequentially. If a customer provides a detail out of order, the AI must note it
and not ask that specific question again.


1. Property Type: Confirm if the property is Residential (house/flat),
Commercial (shop/office), or Industrial (factory).
- Eligibility: Only Residential, Commercial, and Industrial are eligible.
If the property is Agricultural, the customer is not eligible.

2. Ownership Status: Find out if the customer is the sole owner or if it is a
joint property (with family/partners).
- Eligibility: Both Sole and Joint ownership are eligible.

3. Document Availability: Confirm if the customer has the original property
documents ready for verification.
- Eligibility: The customer must have Original Documents available to
proceed.

4. Loan Amount: Ask the customer how much money they are looking to
borrow.
- Eligibility: The amount must be 75,00,000 (75 Lakhs) or less.
5. Occupation & Income Mode: Determine if the customer is Salaried (has a
job)
or Self-Employed (runs a business), and if their income is received in the
bank or cash.
- Eligibility: Both Salaried and Self-Employed are eligible, but the
income must be received via Bank. If the income is in Cash, they are not
eligible.

6. Market Value: Get an estimated current market value of the property.

7. Tenure: Ask how many years they would like to take to repay the loan.
- Eligibility: The repayment period must be between 3 and 15 years.

3. Business Logic & Boundaries

- Immediate Disqualification: At any point in the conversation, if the
customer provides an answer that does not meet the eligibility criteria
(e.g., they say their income is in cash, or the property is agricultural),
the bot must politely inform them that they do not meet the criteria for
this specific offer at this time and end the call.
- The "Transfer" Logic Switch: Our standard flow is for a "Fresh Loan."
However, if a customer mentions they already have an existing loan on the
property or want to reduce their current EMI, the bot must inform the
customer that a specialist for loan transfer will contact them shortly
and then end the call.
- Loan Amount Limits: If a customer requests more than 75 Lakhs, explain the
limit and ask if they would like to proceed with the maximum allowed
amount.
- Post-Qualification Handoff: Once all 7 points are answered and criteria are
met, inform the customer that a senior loan expert will call them back
shortly to provide exact interest rates.

4. Technical Specifications: User Prompt Variables
Please ensure your System Prompt logic accounts for these:
- company_name: Name of the company.
- customer_name: The name of the customer being called.
- agent_name: Your name as the AI assistant.
- agent_gender: Your gender (Must be adhered to strictly).
- current_date / current_day / current_time: For context.
- additional_context_from_rag: Specific product knowledge retrieved.
- language_to_speak: The language you must use (English or Hindi).
- conversation_history: The log of the current chat.
- customer_utterance: The latest thing the customer said.
  
5. Additional Points to Consider (Mandatory)
- Natural Conversation: Do not design the bot to only handle "Yes" or "No"
answers. The bot must handle full sentences, interruptions, and
conversational fillers. Talk like real customers when testing.
- Prompt Length: There is no limit on the length of the system prompt. Our
focus is on absolute accuracy and ensuring every edge case
(disqualifications, transfers, busy states) is covered.
- Handoff Gates: You can only move to the final handoff once all eligibility
questions are asked and answered. If any were skipped earlier due to a
diversion, the AI must go back and ask them.

6. Testing and Submission
To demonstrate your prompt, implement it on a voice platform of your choice
(Retell AI, Bolna, or similar):

1. Sign up for a free trial and create a new agent.
2. Paste your written System Prompt into the instructions and select a
professional voice.
3. Conduct multiple calls acting like a real customer to test logic
accuracy across different scenarios.
4. Submission: Provide the System Prompt text and the Public Link to the Call
Recording & Call Logs (audio + transcript).
