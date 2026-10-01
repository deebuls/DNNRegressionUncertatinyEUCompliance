# Mind Map

1. Idea 1: The Regulatory-Technical Bridge (Position / Methodology Paper)
  * "From Probabilities to Compliance: A Formal Framework Mapping DNN Regression Uncertainty to the EU AI Act and ISO Standards"
2. Domain-Specific Safety Architecture (Systems / Engineering Paper)
  * Safety-Aware Control Loops: Integrating Evidential DNN Regression into ISO 26262/SOTIF Architecture for Heavy Machinery
    - GSN template showing how uncertaitny satisfies EU AIT act article 14 robustness and 15 human oversight

## The GSN claim
“Validated per-output uncertainty estimates provide evidence that the system can identify potentially unreliable predictions and apply an appropriate mitigation, contributing to the argument for robustness under Article 15.”

### Why uncertainty is evidence for robustness
Because of following tests
1. Calibration: predicted confidence corresponds reasonably to observed correctness.
2. Discrimination: uncertain outputs are more likely to be wrong than confident outputs.
3. Defined thresholds: the system rejects, escalates, or requests human review below an uncertainty threshold.
4. Robustness testing: uncertainty remains informative under noise, distribution shift, edge cases, faults, and adversarial inputs.
5. Lifecycle monitoring: calibration and performance are rechecked after updates or deployment.


# EU AI Act articles
## Chapter II (Articles 8–15) requirements for high-risk AI, including:
* Article 9 (Risk Management System): Continuous hazard analysis integrated into your functional safety lifecycle.
* Article 10 (Data and Data Governance): Strict standards for dataset quality, validation, and mitigation of visual detection biases.
* Article 11 & Annex IV (Technical Documentation): Comprehensive technical files detailing architecture, SIL alignment, training, and testing.
* Article 14 (Human Oversight): Design allowing human operators to oversee, override, or halt automated machinery actions.
* Article 15 (Accuracy, Robustness, and Cybersecurity): Ensuring high resilience against computer vision failure modes (adversarial noise, sensor deterioration, lighting changes).
* Article 43 (Conformity Assessment): Undergoing conformity assessment procedures, usually coordinated alongside your SIL 3 machine certification with a Notified Body.



# Summary 

###  EU AI Act Regulation
* Previous : Annex I Machinery / Product Directives (Product Safety Laws)
* New Standard : EU AI Act (Articles 6, 8–15, 50, 80) (Harmonized Law)
* "Shift from static product safety to continuous lifecycle risk management, dataset governance, and human oversight.
* High-Risk designation requiring Notified Body involvement, third-party conformity assessments, and technical documentation (Annex IV).
 
### Industrial Heavy Machinery
* Previous : IEC 61508 / ISO 13849 / IEC 62061 (SIL 1–4 / PL a–e),
* New Standard : ISO/IEC TR 5469 (Functional safety and AI systems)
* Replaces single-block execution with Safety Architecture Patterns (DNN + Deterministic SIL 3 rule-based monitor/wrapper)
* DNN outputs are constrained by a deterministic hardware/software safety barrier certified to high SIL levels.

### Automotive
* Previous : ISO 26262 (ASIL A–D)
* New Standard : ISO 21448 (SOTIF) & ISO/PAS 8800
* Shift from hardware/software fault elimination to managing performance insufficiencies and ODD triggering conditions.
* SOTIF addresses what happens when the DNN operates perfectly according to code, but still fails due to sensor limitations, environment edge cases, or AI generalization boundaries.
* Third-Party SOTIF process audits (e.g., TÜV), SOTIF Safety Case assessments, and UN R157/EU 2022/1426 vehicle type-approval.

### Aviation & Aerospace
* Previous : DO-178C / ED-12C (DAL A–E)
* New Standard : EUROCAE ED-324 / SAE ARP6983 & EASA AI Roadmap
* Shift from 100% Structural Code Coverage (MC/DC) to Learning Assurance (Data Coverage, Data Completeness, Bias Mitigation).
* Restricting AI to maximum DAL C initial deployment; requiring runtime deterministic safeguards and explainability metrics.

### Medical Devices (SaMD)
* Previous : IEC 62304 & ISO 14971 (Safety Classes A–C)
* New Standard : FDA PCCP, Good Machine Learning Practice (GMLP), AAMI TIR34971
* Shift from static, one-time software releases to Monitored Algorithmic Evolution and data drift management.
* Predetermined Change Control Plans (PCCP) pre-authorizing adaptive algorithm updates without requiring full re-clearance.





# Paper structure 
Structure the paper around three topics: 
1. System Architecture,
2. Compliance Mapping, and
3. Experimental Validation.

| Regulation / Standard | Standard Requirement                           | Single-Pass NLL Equivalent Metric                                                     | System Action                                         |
|-----------------------|------------------------------------------------|---------------------------------------------------------------------------------------|-------------------------------------------------------|
| EU AI Act (Art. 15)   | Resiliency against OOD / corrupted data        | Variance thresholding: $\sigma^2_{total} > \tau_{OOD}$                                | Trigger system audit log & degrade capability         |
| ISO 21448 (SOTIF)     | Boundary check for Area 3 (Unknown Unsafe)     | $3\sigma$ Spatial Margin: $[\mu - 3\sigma, \mu + 3\sigma] \subset \text{Safety Zone}$ | Halt docking if safety zone is breached               |
| ISO/PAS 8800          | Runtime ML Performance Insufficiency Detection | Epistemic/Aleatoric split via Evidential NLL                                          | Trigger Minimal Risk Maneuver (MRM)                   |
| ISO/IEC TR 5469       | Non-deterministic risk mitigation              | Deterministic Single-Pass Execution Profile                                           | Pass timing & WCET (Worst-Case Execution Time) checks |


# Papers

1. [PASTA: A Scalable Framework for Multi-Policy AI Compliance Evaluation](https://arxiv.org/pdf/2601.11702)
  * LLM Tool which helps user to select appropriate compliance

2. [Making the Relationship between Uncertainty
Estimation and Safety Less Uncertain ](https://past.date-conference.com/proceedings-archive/2020/pdf/1030.pdf#:~:text=How%20does%20it%20connect%20to%20classical%20safety,rationales%20that%20can%20for%20sure%20be%20identified.)

3. [The Dilemma of Uncertainty Estimation for General Purpose AI in the European
Union Artificial Intelligence Act ] (https://arxiv.org/pdf/2408.11249)

4. https://arxiv.org/html/2512.13907v1 
    R2.4: Accuracy & Uncertainty : ISACA manual (Sec. 1.4.3) : M2.7: Model calibration — Review whether confidence scores are appropriately aligned with model performance. 
    

