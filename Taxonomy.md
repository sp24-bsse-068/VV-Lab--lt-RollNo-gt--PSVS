| Category | Definition | Example |
| :--- | :--- | :--- |
| **Ambiguity** | Requirement has multiple plausible interpretations. | "Chambers shall be kept at a safe temperature." (What temperature is safe?) |
| **Vagueness** | Use of non-quantifiable or subjective terms. | "Seed samples with low viability shall be flagged promptly." (What constitutes "promptly"?) |
| **Incompleteness** | Missing necessary parameters, conditions, or exception handling. | Specifying that boxes can be withdrawn, but omitting the required identification documentation format. |
| **Contradiction** | Two or more statements mutually exclude each other or create a logical clash. | S4 states only the depositor may withdraw a box, while S5 permits the vault authority to release any box to any requesting party without depositor consent. |
| **Non-Verifiability** | Requirement cannot be tested objectively or measured. | "The system shall keep a good audit trail." ("Good" is subjective and untestable). |
| **Redundancy** | Repetitive or overlapping statements that add no new constraint. | Separate requirements stating chambers must be cold and temperatures must never rise above -18°C (overlapping with S6 and S7). |
| **Infeasibility** | Technical or physical constraints make implementation impossible or contradictory to known laws. | Maintaining Chamber 4 at -18°C or below while simultaneously allowing it to be warmed to 0°C during maintenance without specifying cooldown/safeguard limits or box relocation (S7 vs S8). |
| **Untraceability** | Lack of clear lineage, identifier, or ability to track source and downstream allocations. | Requirements mentioning "depositor" or "requesting party" without a defined institutional registry reference model. |

## Question 2
| Defect ID | Req ID | Category | Description | Evidence | Severity | Suggested fix | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **D01** | S1 | Ambiguity | "Registered depositors" lacks definition of registry criteria. | S1 text | Medium | Define registration criteria and authority. | Open |
| **D02** | S2 | Vagueness | "Large number" is subjective and non-quantifiable. | S2 text | Low | Replace with precise maximum box capacity per chamber. | Open |
| **D03** | S3 | Incompleteness | Omits total aggregate vault capacity across all chambers. | S3 text | Low | Add total capacity constraint. | Open |
| **D04** | S4 vs S5 | Contradiction | S4 restricts withdrawal exclusively to the owner, whereas S5 allows the authority to release any box to any requester in an emergency. | S4 & S5 | High | Modify S4 to include emergency override exception clause explicitly. | Open |
| **D05** | S6 | Ambiguity | "Safe temperature" is undefined. | S6 text | High | Specify exact numeric safe temperature range (e.g., -18°C to -20°C). | Open |
| **D06** | S6 vs S7 | Redundancy | S6 ("safe temperature") is fully subsumed and overlapped by S7 (≤ -18°C). | S6 & S7 | Low | Combine S6 and S7 into a single temperature requirement. | Open |
| **D07** | S7 vs S8 | Infeasibility | Warming a chamber to 0°C for maintenance (S8) violates the strict ceiling of -18°C (S7) unless safe seed relocation is mandated. | S7 & S8 | High | Add an explicit exception clause in S7 for maintenance periods with box transfer protocols. | Open |
| **D08** | S9 | Vagueness | "Promptly" is subjective; no time limit given. | S9 text | Medium | Define prompt threshold (e.g., "within 24 hours of viability testing"). | Open |
| **D09** | S9 | Incompleteness | Viability testing frequency and testing method standards are missing. | S9 text | Medium | Specify testing schedule (e.g., annual germination tests). | Open |
| **D10** | S10 | Ambiguity | "Per year" does not specify calendar year vs. rolling 12-month period. | S10 text | Low | Clarify as "per calendar year (Jan 1 – Dec 31)". | Open |
| **D11** | S11 | Vagueness | "Re-inspection" lacks criteria or standards for passing inspection. | S11 text | Medium | Define re-inspection standards (e.g., viability ≥ 85%, pest-free). | Open |
| **D12** | S12 | Non-verifiability | "Good audit trail" is subjective and untestable. | S12 text | High | Specify exact audit attributes (timestamp, user ID, action type, log retention period). | Open |
| **D13** | S3 vs S4 | Incompleteness | Capacity limits (S3) do not account for box volume variance or slot reservations. | S3 & S4 | Low | Define standardized box dimensions and slot allocations. | Open |
| **D14** | S5 | Ambiguity | "Emergency" is undefined; who declares it? | S5 text | High | Define emergency criteria and authorized declarant role. | Open |
| **D15** | S10 vs S4 | Contradiction | S10 restricts a depositor to 20% withdrawal per year, but S5 allows vault authority to release boxes without depositor limits during emergencies. | S5 & S10 | Medium | Clarify that emergency releases override annual quota limits. | Open |



## Question 3
| Defect ID | Req ID | Category | Description | Evidence | Severity | Suggested fix | Status |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **D01** | S1 | Ambiguity | "Registered depositors" lacks definition of registry criteria. | S1 text | Medium | Define registration criteria and authority. | Open |
| **D02** | S2 | Vagueness | "Large number" is subjective and non-quantifiable. | S2 text | Low | Replace with precise maximum box capacity per chamber. | Open |
| **D03** | S3 | Incompleteness | Omits total aggregate vault capacity across all chambers. | S3 text | Low | Add total capacity constraint. | Open |
| **D04** | S4 vs S5 | Contradiction | S4 restricts withdrawal exclusively to the owner, whereas S5 allows the authority to release any box to any requester in an emergency. | S4 & S5 | High | Modify S4 to include emergency override exception clause explicitly. | Open |
| **D05** | S6 | Ambiguity | "Safe temperature" is undefined. | S6 text | High | Specify exact numeric safe temperature range (e.g., -18°C to -20°C). | Open |
| **D06** | S6 vs S7 | Redundancy | S6 ("safe temperature") is fully subsumed and overlapped by S7 (≤ -18°C). | S6 & S7 | Low | Combine S6 and S7 into a single temperature requirement. | Open |
| **D07** | S7 vs S8 | Infeasibility | Warming a chamber to 0°C for maintenance (S8) violates the strict ceiling of -18°C (S7) unless safe seed relocation is mandated. | S7 & S8 | High | Add an explicit exception clause in S7 for maintenance periods with box transfer protocols. | Open |
| **D08** | S9 | Vagueness | "Promptly" is subjective; no time limit given. | S9 text | Medium | Define prompt threshold (e.g., "within 24 hours of viability testing"). | Open |
| **D09** | S9 | Incompleteness | Viability testing frequency and testing method standards are missing. | S9 text | Medium | Specify testing schedule (e.g., annual germination tests). | Open |
| **D10** | S10 | Ambiguity | "Per year" does not specify calendar year vs. rolling 12-month period. | S10 text | Low | Clarify as "per calendar year (Jan 1 – Dec 31)". | Open |
| **D11** | S11 | Vagueness | "Re-inspection" lacks criteria or standards for passing inspection. | S11 text | Medium | Define re-inspection standards (e.g., viability ≥ 85%, pest-free). | Open |
| **D12** | S12 | Non-verifiability | "Good audit trail" is subjective and untestable. | S12 text | High | Specify exact audit attributes (timestamp, user ID, action type, log retention period). | Open |
| **D13** | S3 vs S4 | Incompleteness | Capacity limits (S3) do not account for box volume variance or slot reservations. | S3 & S4 | Low | Define standardized box dimensions and slot allocations. | Open |
| **D14** | S5 | Ambiguity | "Emergency" is undefined; who declares it? | S5 text | High | Define emergency criteria and authorized declarant role. | Open |
| **D15** | S10 vs S4 | Contradiction | S10 restricts a depositor to 20% withdrawal per year, but S5 allows vault authority to release boxes without depositor limits during emergencies. | S5 & S10 | Medium | Clarify that emergency releases override annual quota limits. | Open |





