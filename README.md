# AI-Assisted Customer Onboarding Health Check

## What I built
A lightweight no-code workflow small experiment I built to explore how AI can support Customer Success teams. It uses structured customer onboarding information to identify risks, highlight missing context, recommend next actions, and draft a customer follow-up. The workflow is designed to keep human judgment in the loop rather than treating AI output as authoritative.

## Why I built it
Customer onboarding data is often spread across notes, CRM fields, implementation updates, and support issues. A CSM can lose time reconstructing the situation before deciding what to do next. This project tests whether AI can create a useful first-pass review while keeping the human responsible for validation and action.

## Inputs
The workflow takes a small structured record containing:
- Customer / segment
- Days since kickoff
- Target go-live date
- Current milestone
- Open blockers
- Product usage / activation signal
- Training status
- Stakeholder engagement
- Support issues
- CSM notes

## AI prompt
The model is asked to:
1. Summarize current onboarding status in 3 bullets.
2. Flag risk signals and explain the evidence for each one.
3. Identify missing information that prevents a confident assessment.
4. Recommend the next 3 actions, assigning a suggested owner and urgency.
5. Draft a short customer-facing follow-up that does not invent facts.
6. Return a confidence level and explicitly separate facts from inference.

## Human review rule
No AI recommendation is treated as final. The CSM validates every risk flag and action against the source data before contacting the customer or changing an account plan.

## What I learned
The most useful output was not the summary. It was the missing-information section. Forcing the model to state what it does not know reduces false confidence and makes the review more operationally useful. I also found that structured inputs produce better recommendations than pasting an unstructured block of notes.

## Next iteration
I would connect the workflow to a CRM or onboarding platform, add a simple scoring rubric for time-to-first-value and stakeholder engagement, and compare AI-generated risk flags against actual CSM decisions over time.

## Tools
- ChatGPT / LLM
- Spreadsheet-style structured input
- Human validation

## Sample data
All example data in this project is synthetic and contains no customer or employer information.

##walkthrough
##README.md
Explains the project, workflow, and lessons learned.

##customer_onboarding_prompt.md
The reusable AI prompt used to evaluate onboarding health.

##sample_customer_data.csv
Synthetic customer onboarding data used for testing.
