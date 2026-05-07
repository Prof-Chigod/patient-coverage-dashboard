# Patient-coverage-dashboard-2024
An interactive Power BI dashboard analyzing patient coverage, insurance claims, billing trends, and payment outcomes.
# Overview of the Dashboard
The Medical Claims and Patient Insurance Coverage 2024 project is built around the real mechanics of how claims move through the healthcare system. Each field in the dataset represents a checkpoint in that journey; from the moment a patient receives care to the final outcome of payment or denial.
## At its core, the dataset captures three interconnected dimensions:
- **Clinical detail:** Procedure Code and Diagnosis Code anchor each claim in the medical
reality of what was done and why.
- **Financial flow:** Billed Amount, Allowed Amount, Paid Amount, and AR Status reveal the
negotiation between providers and insurers, showing the gap between what is charged, what is
approved, and what is actually paid.
- **Operational process:** Claim Status, Reason Code, Follow-up Required, and Outcome
highlight the administrative hurdles that determine whether a claim is resolved smoothly or
caught in delays and denials.
By weaving these fields together, the dataset doesn’t just log transactions; it tells the story of
healthcare access, provider accountability, and insurance coverage in 2024. The accompanying
dashboards transform this complexity into clear visual narratives, allowing users to spot
inefficiencies, track patient impact, and evaluate insurer performance at a glance.
This project is unique because it treats claims data not as static records, but as a living system
of interactions between patients, providers, and insurers. It’s designed to surface insights that
matter: where coverage breaks down, where costs escalate, and where follow-ups signal
deeper structural issues
---
# Dataset Fields
The dataset is designed to capture the complete journey of a medical claim, from the moment a
service is provided to the final resolution. Each field plays a role in telling that story:
- **Claim ID:** A unique identifier that distinguishes each claim record.
- **Provider ID:** Identifies the healthcare provider who submitted the claim.
- **Patient ID:** An anonymized code representing the patient linked to the claim.
- **Date of Service:** The exact date when the medical service was delivered.
- **Billed Amount:** The total amount charged by the provider for the service.
- **Procedure Code:** A standardized code (such as 99231) that specifies the medical
procedure performed.
- **Diagnosis Code:** A standardized code (such as A02.1) that indicates the patient’s
diagnosis.
- **Allowed Amount:** The portion of the billed amount approved by the insurer after
adjustments.
- **Paid Amount:** The actual payment made by the insurer to the provider.
- **Insurance Type:** The type of insurance policy covering the patient (Medicare, Commercial,
Self-pay, etc.).
- **Claim Status:** The current state of the claim; whether it is paid, under review, or denied.
- **Reason Code:** A code explaining why a claim was denied, paid, or partially paid.
- **Follow-up Required:** A flag indicating whether additional action is needed to resolve the
claim.
- **AR Status:** The Accounts Receivable status, showing whether payment is pending or
closed.
- **Outcome:** The final resolution of the claim, such as paid, partially paid, or denied.
---
# Working with the Dataset
The dataset came pre-cleaned, which allowed me to focus on structuring and preparing it for
analysis rather than spending time on heavy preprocessing. My workflow in Power BI was
designed to ensure accuracy, usability, and meaningful insights:
1. ## Import and Structure
- I imported the dataset into Power BI and reviewed it in table format.
- To avoid misleading aggregations, I set key identifiers — Patient ID, Provider ID, Procedure
Code, Claim ID, and Diagnosis Code to **“Don’t Summarize.”** This ensured that these
categorical fields were treated as unique labels rather than numerical values.
## Clean dataset
<img width="1259" height="531" alt="claim_clean_dataset" src="https://github.com/user-attachments/assets/85e12ac4-4702-45df-8aec-5f9b0ceb4e1a" />

2. ## Date Formatting for Deeper Insights
- I reformatted the Date of Service field by creating two new columns: Month and Day.
- This separation allows for granular analysis, such as identifying which month had the highest
or lowest insurance payments, and which day showed unusual spikes or drops in claim activity.
- I did not create a separate Year column since the dataset is exclusively for 2024, making
year-based comparisons unnecessary.
## Month
<img width="1142" height="618" alt="image" src="https://github.com/user-attachments/assets/2a829c3a-70f0-4697-9487-d2efd2a00ca6" />
## Day
<img width="1203" height="624" alt="image" src="https://github.com/user-attachments/assets/25abb2a8-4dda-4f22-9da4-ee1ad48cc475" />











