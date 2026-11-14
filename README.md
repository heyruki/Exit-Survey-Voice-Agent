Exit Survey Voice Agent
A voice AI agent, built on ElevenLabs Agents, that runs short exit interviews with customers who have just cancelled subscription. 
It finds out why they left, collects consistent ratings, and gets the feedback to the team.

The problem
Most customers who cancel never explain why. 
Exit surveys sent by email get few replies, and the answers are hard to compare, a human call gets better answers but doesn't scale.
I wanted something in between: a quick, friendly voice conversation that a customer can do in about three minutes, with clean data at the end.

What it does
The agent runs a structured exit interview in about 3 minutes:

1. Asks why they cancelled and lets them talk, then quietly sorts the reason into one of these categories:
Project ended or no ongoing need
Platform performance or technical issues
Cost or budget
Building in-house
Switched to another vendor
Other

2. Asks what they're moving to, but only if they're switching vendor or building in-house.

3. Collects 1–5 ratings, one at a time, for:
The company overall
Extraction accuracy and speed
System stability and reliability
Customer support and account management

4. Asks how likely they are to return if those areas improved (1–5).

5. Asks what would have stopped them cancelling.

6. Confirms the account email by reading it back spelled out, so the feedback is linked to the right account.

7. Thanks them and ends the call.

Everything except the email is optional. If a customer answers a later question early, the agent doesn't ask it again.

Design choices
It doesn't try to win customers back. It offers no discounts and never asks them to reconsider. The customer has already left, and the goal is honest feedback, not a sales pitch.
It closes the loop on every answer. After each answer it confirms the feedback was captured and is going to the team, so the customer feels heard.
It doesn't judge answers. It avoids phrases like "that's totally fair" or "I understand", which can sound scripted or dismissive.
Every rating ends up as a clean number. If someone answers in words or a range ("like a 3 or 4"), the agent asks once which whole number fits.
It handles anger calmly. It lets the customer finish, apologises once, says back what it heard, and never defends the company.
It's brisk and warm. It keeps turns to one or two sentences, asks one question at a time, and never reads out lists.

Guardrails
No promises of fixes, refunds, callbacks or timelines.
No access to accounts or billing. Requests about those are flagged to the team and sent to support.
No comments on competitors, and it never suggests the customer was at fault.
It never asks for passwords or payment details.
It ends the call politely if a customer keeps being abusive.
It says it's an AI if asked.

Try it yourself
Create a new agent in ElevenLabs Agents.
Paste the contents of the prompt file (attached) into the System prompt.
Paste this into the separate First message field:
[warmly] Thanks for taking your time to share your feedback. We will aim to wrap this up in 2 to 3 minutes. First, could you tell me what led you to cancel your account?
Replace [Agent Name] and [Company Name] with your own.
Turn on the end_call system tool so the agent can end the call.
Change the rating categories to fit your product.

What I learned
The wording sets the tone more than the voice settings do. Telling the agent to be brisk, with short sentences, made it sound calm without sounding slow.
Banning filler phrases matters. Without that rule, the agent kept saying "that makes sense", which sounded robotic in an exit interview.
Structured data needs explicit rules. Asking once for a whole number turned vague answers into ratings I could actually compare.

Feedback and ideas are welcome. Find me on X at @heyheyruki.
