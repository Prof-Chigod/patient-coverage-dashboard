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
- **Insurance Type:** The type of insurance policy covering the patient (Medicare, Commercial, Self-pay, etc.).
- **Claim Status:** The current state of the claim; whether it is paid, under review, or denied.
- **Reason Code:** A code explaining why a claim was denied, paid, or partially paid.
- **Follow-up Required:** A flag indicating whether additional action is needed to resolve the
claim.
- **AR Status:** The Accounts Receivable status, showing whether payment is pending or
closed.
- **Outcome:** The final resolution of the claim, such as paid, partially paid, or denied.
---
# Working with the Dataset
The dataset came pre-cleaned, which allowed me to focus on structuring and preparing it for analysis rather than spending time on heavy preprocessing. My workflow in Power BI was designed to ensure accuracy, usability, and meaningful insights:
1. ## Import and Structure
- I imported the dataset into Power BI and reviewed it in table format.
- To avoid misleading aggregations, I set key identifiers — Patient ID, Provider ID, Procedure
Code, Claim ID, and Diagnosis Code to **“Don’t Summarize.”** This ensured that these
categorical fields were treated as unique labels rather than numerical values.
## Clean dataset
<img width="1259" height="531" alt="claim_clean_dataset" src="https://github.com/user-attachments/assets/85e12ac4-4702-45df-8aec-5f9b0ceb4e1a" />

2. ## Date Formatting for Deeper Insights
- I reformatted the Date of Service field by creating two new columns: Month and Day.
- This separation allows for granular analysis, such as identifying which month had the highest or lowest insurance payments, and which day showed unusual spikes or drops in claim activity.
- I did not create a separate Year column since the dataset is exclusively for 2024, making
year-based comparisons unnecessary.
## Month
<img width="1142" height="618" alt="image" src="https://github.com/user-attachments/assets/2a829c3a-70f0-4697-9487-d2efd2a00ca6" />

## Day
<img width="1203" height="624" alt="image" src="https://github.com/user-attachments/assets/25abb2a8-4dda-4f22-9da4-ee1ad48cc475" />

3. ## Analytical Purpose
- These transformations were not just technical steps; they were intentional design choices to
make the dataset more story-driven.
- By focusing on identifiers and time-based breakdowns, the dataset now supports questions like:
- Which providers consistently receive higher reimbursements?
- Are certain diagnoses more likely to be denied or underpaid?
- Do specific months show patterns of delayed claims or higher patient out-of-pocket
costs?
---
# The Dashboard Story
1. ## General Dashboard
<img width="1059" height="595" alt="image" src="https://github.com/user-attachments/assets/969ce5c1-f6f7-4273-a57d-a4ae8b365066" />

## Key Finding
When the dataset was brought into Power BI, the first goal was to make the numbers speak.
The dashboard began with filters for **Month**, **Day**, **Date of Service**, **Outcome**, and
**Claim Status**, giving users the ability to slice the data from multiple angles.

The financial cards immediately set the stage: providers billed a total of **297k**, insurers
allowed **223k**, and ultimately paid **201k**. This simple trio of numbers told the story of the
gap between what providers charge and what insurers agree to cover.

Digging deeper, the **Reason Code analysis** uncovered a striking pattern. The most common
issue patients faced was *“Authorization not obtained.”* This single administrative hurdle
accounted for the highest patient count, showing how paperwork; not medicine, often
determines outcomes.

The **Provider distribution** added another layer to the story. Claims marked as *“Paid”* were
most often linked to an AR Status of *“Partially Paid.”* Meanwhile, claims with the outcome
*“Partially Paid”* had the least AR Status at *“Denied.”* This revealed a nuanced relationship
between payment outcomes and receivables, suggesting that even *“paid”* claims often carried
hidden complexities.

Time-based filters brought seasonal variation into focus. **June** stood out with the highest
number of Provider IDs, while **September** recorded the lowest. This raised questions about
operational cycles or policy changes that might influence claim activity across the year.

Finally, the **Insurance Type comparison** told a surprising story of parity. Both **Commercial**
and **Medicaid** insurance types had the same total number of Claim IDs, and their financial
metrics; billed, allowed, and paid amounts, matched exactly. This suggested that, at least in
2024, these two insurance categories behaved in remarkably similar ways.
<img width="1049" height="590" alt="image" src="https://github.com/user-attachments/assets/4f1d88a3-be85-44d8-bcef-6c6170219d7d" />

## Key Finding
On **Friday, May 10, 2024,** the dashboard revealed a very different picture compared to the general trends. This single day of service carried its own story.

The **Reason Code analysis** showed that *“Pre-existing condition”* was the most frequent issue, with the highest number of Patient IDs. When grouped by **Diagnosis Code,** the same reason also carried the highest number of claims requiring follow-up marked as *“Yes.”* This
highlighted how certain medical histories can trigger both administrative and clinical complexity.

Looking at **Insurance Types,** both **Medicaid** and **Medicare** recorded the lowest number of Claim IDs on this date. Yet, in the *“Under Review”* Claim Status, the dashboard showed that Medicaid and Commercial insurance types had the highest **Allowed Amounts,** suggesting that while fewer claims were filed, the ones under review carried significant financial weight.

Financially, **Medicaid** stood out across the board. It recorded the highest totals in **Billed
Amount, Allowed Amount, and Paid Amount,** making it the dominant insurance type for this
day’s claims activity.

The **Provider Distribution** added another twist: outcomes of *“Partially Paid”* and *“Denied”* were tied when compared by **Outcome and AR Status.** This tie suggested that providers faced equal challenges in navigating partial payments and outright denials, underscoring the tension between reimbursement and rejection.

3. ## Sunday, Denied Outcome Dashboard
   <img width="1064" height="593" alt="image" src="https://github.com/user-attachments/assets/35e313db-f1e0-4321-ab98-cec9183ee186" />
## Key Finding

When the dashboard was filtered to **Sunday** and the outcome set to **Denied,** a very
distinct pattern emerged.

The financial cards told a surprising story: under this filter, **Commercial insurance** carried the highest totals across **Billed Amount, Allowed Amount, and Paid Amount,** while **Medicaid** consistently recorded the lowest. This contrast highlighted how denial outcomes don’t always align with lower financial activity; infact, the largest amounts were tied to denied claims under Commercial insurance.

Looking closer at **Claim Status,** the *“Under Review”* category revealed that **Commercial** insurance led the way in Allowed Amounts, followed by **Self-Pay.** Commercial also had the highest number of Claim IDs under the denied outcome, reinforcing its dominance in this filtered view

The **Diagnosis grouping** added another layer: the reason code *“Incorrect billing information”* peaked here, with both *“Yes Follow-up”* and *“No Follow-up”* counts reaching their highest under this same reason. This suggested that billing errors were a major driver of denied claims, regardless of whether follow-up was required.

Finally, the **Provider Distribution** tied the story together. Under the denied outcome, the highest AR Status was also *“Denied,”* while the least was *“Partially Paid.”* This alignment showed that denial cascaded through the claims process, leaving little room for partial resolution.

4. ## June, Claim Status “Paid” Dashboard
<img width="1050" height="586" alt="image" src="https://github.com/user-attachments/assets/70231064-e6cc-405a-a0f6-8fd9a569f006" />


## Key Finding
June told a different story when the dashboard was filtered to show only claims with the status **“Paid.”**

The **Reason Code analysis** revealed that *“Missing documentation”* was the most common issue by patient count, while *“Service not covered”* appeared the least. This suggested thateven among paid claims, documentation gaps remained a recurring challenge.

When grouped by **Diagnosis Code,** the reason code *“Pre-existing condition”* had the lowest number of claims requiring a *“Yes”* follow-up. In the *“No”* follow-up section, *“Pre-existing condition”* and *“Missing documentation”* tied at the bottom, showing that these issues were less likely to be resolved without further action.

The **Provider Distribution** added another layer: the outcome *“Partially Paid”* combined with AR Status *“Partially Paid”* recorded the highest number of Provider IDs. This highlighted that even in a month dominated by paid claims, partial payments were still a significant reality for providers.

Financially, **Self-Pay insurance type** stood out. It recorded the highest totals across **Billed Amount, Allowed Amount, and Paid Amount,** while **Medicare** consistently had the lowest; both in financial metrics and total Claim IDs. This contrast underscored the weight of out-of-pocket payments compared to government-backed coverage.

Finally, under **Total Allowed Amount by Claim Status “Paid”,** **Commercial insurance** ranked second to the least. This finding suggested that while Commercial insurance was active in June, its contribution to allowed amounts lagged behind other types, raising questions about coverage generosity

5. ## Outcome “Partially Paid” & Claim Status “Under Review” Dashboard
<img width="1058" height="589" alt="image" src="https://github.com/user-attachments/assets/4aa5149b-058b-4970-bda2-9a5cd859e3ed" />

## Key Finding

When the dashboard was filtered to show claims with the outcome **“Partially Paid”** and status **“Under Review,”** the data revealed a layered story of administrative friction and financial imbalance.

The **Reason Code analysis** showed that *“Lack of medical necessity”* had the lowest patient count overall, while *“Duplicate claim”* ranked as the third highest. This contrast highlighted how some denials stem from clinical justification, while others are purely administrative errors

On the **Provider Distribution,** the outcome *“Partially Paid”* combined with AR Status *“Open”* recorded the highest number of providers. Meanwhile, *“Pending”* and *“Denied”* tied as the third highest, showing that providers often linger in uncertainty when claims are partially resolved.

Grouping by **Diagnosis Code** uncovered another familiar pattern: *“Incorrect billing information”* once again surfaced, this time with the highest number of diagnosis codes under *“Yes Follow-up.”* This reinforced its recurring role as a major driver of claim issues. In contrast, *“Service not covered”* was the least frequent under *“No Follow-up,”* suggesting that coverage gaps rarely end without further action.

The **Insurance Type analysis** added financial depth. **Commercial** and **Medicaid** tied for the highest total Claim IDs, but when measured by **Billed, Allowed, and Paid Amounts, Medicaid** came first, followed closely by **Commercial.** This showed that Medicaid carried more financial weight despite equal claim volume. On the other end, under the *“Under Review”* claim status, **Self-Pay** and **Medicare** recorded the lowest totals in Allowed Amounts, underscoring their limited role in this filtered view.

---

# Behavioral Patterns Across Dashboards

1. ## Documentation and Administrative Barriers Dominate
2. 
- Across multiple dashboards, issues like *“Authorization not obtained”* and *“Missing documentation”* consistently appear as top reasons for claim problems.
- 
- Even when claims are ultimately marked as *Paid*, documentation gaps remain a recurringtheme. This shows that administrative processes, not medical necessity, are often the biggest hurdle in claim resolution.
- 
2. ## Insurance Type Contradictions
  
- **Commercial insurance** frequently appears at both extremes: it records the highest totals in
denied outcomes (Sunday filter) and also ranks high in allowed amounts under review.

- **Medicaid** shows dual behavior: sometimes the least in claim counts (May 10, Sunday), yet bat other times the highest across billed, allowed, and paid amounts (May 10).

- **Self-Pay** consistently emerges as financially dominant in certain contexts (June Paid), highlighting the burden patients carry when coverage is absent.

3. ## Provider Distribution Nuances
- Providers often face outcomes where *“Partially Paid”* dominates AR Status, even under *“Paid”* claim status.

- Denied outcomes reinforce denial at the AR level, leaving little room for partial resolution.
  
- This pattern suggests providers are caught between partial reimbursements and outright denials, with few clean *“paid”* outcomes.

4. # Seasonal and Date-Specific Variations
   
- **June** stands out with the highest provider activity, while **September** shows the least.

- Specific dates (like May 10) reveal unique anomalies; such as Medicaid dominating billed, allowed, and paid amounts despite having fewer claim IDs.
- Sundays show denial-heavy behavior, with Commercial insurance leading in denied claims, suggesting possible operational or policy-driven cycles tied to days of the week

5. Reason Codes as Root Causes

- *Pre-existing condition* and *Incorrect billing information* repeatedly surface as critical drivers of denied claims and follow-ups.

- These codes highlight systemic issues: medical history exclusions and billing errors are not just isolated problems, but recurring behavioral patterns across insurers and providers.

This **behavioral analysis** transforms the dashboards from **static visuals** into a **case study of systemic inefficiencies and contradictions** in **medical claims and insurance coverage for 2024.**

# Tools and Technologies

- **Power BI:** Used to import, structure, and visualize the dataset with interactive filters and card summaries.
- 
- **Google Sheets:** Provided an accessible platform to host and share the interactive dashboard with non-technical users.
  
- **Data Preparation:** Focused on formatting identifiers and creating new time-based columns to enable deeper analysis.
- 
- **GitHub:** Served as the central hub for documentation, dataset description, and storytelling of dashboard insights

# Personal learning from projects

### **1. Teamwork and Collaboration**
Working on this project with a teammate taught me the importance of collaboration in data projects. We had to divide responsibilities, share ideas, and constantly review each other’s work to ensure accuracy and consistency. I learned that effective teamwork is not just about splitting tasks, but about combining different perspectives to achieve a stronger outcome. Through collaboration, we were able to solve challenges faster and improve the overall quality of the analysis.

### **2.Data Visualization in Stages**
One major lesson I learned was that data visualization is a gradual process rather than a one-step activity. Before creating meaningful dashboards, the data wa already clean, so we transformed properly. As the project progressed, I discovered that building visuals in stages helped reveal patterns step by step, making the final dashboard more insightful and easier to understand.

### **3.How Problems Can Be Categorized**
The project showed me that complex datasets become easier to analyze when problems are broken into categories. By separating claims based on insurance types, payment status, denial reasons, and provider performance, we could identify trends more effectively. This approach helped me understand that categorization is essential in analytics because it simplifies large amounts of information into manageable insights.

### **4.How to Interpret Stories from Data**
Beyond numbers and charts, I learned that data always tells a story. The analysis revealed patterns about insurance claims, provider challenges, and payment inconsistencies that would not have been obvious at first glance. I discovered that interpreting data requires looking beyond the figures to understand the real-world situations they represent, making analysis more meaningful and impactful.

### **5.Data Communication**
This roject improved my ability to communicate insights clearly through dashboards and presentations. I realized that even accurate analysis can lose value if it is not presented in a simple and understandable way. Learning how to explain trends, highlight key findings, and guide viewers through the dashboard helped me understand the importance of effective data communication in decision-making.

# Author and Co-author

**Author:** **Blessing-Chinaza - Data Analyst| Medical Laboratory Scientist| Virtual Assistant** -
Led the project design, dataset preparation, Power BI dashboard development, and storytelling of insights.

**Co-author:** **Godfrey-Chimaobi-Kelvin; Data and Financia Analyst** — Contributed to data validation, supported visualization design, and assisted in documenting analytical findings.

---
# Contact
## For inquiries, collaborations, or feedback regarding this project:
[Connect with me on LinkedIn](https://www.linkedin.com/in/chigod)

You can also

[Connect with my partner on LinkedIn](https://www.linkedin.com/in/blessing-nwokike/)



