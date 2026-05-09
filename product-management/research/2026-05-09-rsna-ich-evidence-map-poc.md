# RSNA evidence map POC: intracranial hemorrhage triage

Purpose: panel-ready proof of concept showing how RSNA-owned and RSNA-published evidence could be organized into an "AI Trust Passport" for one narrow clinical wedge.

Important: This is product/design framing, not legal, regulatory, clinical, or purchasing advice. Any regulated product claim, medical-device classification, validation plan, or customer-facing safety statement would need review by qualified regulatory, quality, clinical, legal, and human-factors experts.

## Panel version

If asked whether RSNA has enough evidence to support an evidence-map product, the safest answer is:

> We tested one narrow wedge: AI triage for intracranial hemorrhage on noncontrast head CT. For that wedge, RSNA does appear to have enough public evidence to build a credible first evidence map: a large RSNA-ASNR challenge dataset, RSNA journal articles on clinical workflow and diagnostic performance, and RSNA-published work on data-labeling limitations and model supervision. That does not prove a broad platform yet, but it is enough to justify a focused POC.

## Wedge definition

| Field | POC assumption |
|---|---|
| Clinical task | Triage and prioritization of suspected intracranial hemorrhage (ICH) on noncontrast head CT |
| Primary users | Radiology leaders, neuroradiologists, imaging informatics leaders, AI governance committees, health-system buyers |
| Buyer question | "Can we trust this class of AI tool enough to evaluate, purchase, deploy, and monitor it responsibly?" |
| Product concept | Evidence map / AI Trust Passport that summarizes peer-reviewed evidence, dataset provenance, workflow impact, known limitations, implementation guardrails, and open evidence gaps |
| Geography | US-first assumption for the panel story |
| Regulatory posture | Informational evidence product, not a diagnostic device, unless future functionality makes patient-specific recommendations or influences clinical decisions directly |

## Evidence map snapshot

| Evidence layer | What RSNA evidence shows | Source examples | Confidence | Product implication |
|---|---|---|---|---|
| Dataset foundation | RSNA and ASNR created a large public brain CT hemorrhage dataset with expert labels across five hemorrhage subtypes. | Flanders et al., "Construction of a Machine Learning Dataset through Collaboration: The RSNA 2019 Brain CT Hemorrhage Challenge," Radiology: Artificial Intelligence, 2020. DOI: [10.1148/ryai.2020190211](https://doi.org/10.1148/ryai.2020190211) | High | RSNA can credibly anchor the evidence map in dataset provenance, label methodology, and known dataset limitations. |
| Clinical performance | A deployed AI-based ICH detection tool showed 93.0% diagnostic accuracy, 87.2% sensitivity, and 97.8% negative predictive value in 4,450 emergent noncontrast head CT exams. | Seyam et al., "Utilization of Artificial Intelligence-based Intracranial Hemorrhage Detection on Emergent Noncontrast CT Images in Clinical Workflow," Radiology: Artificial Intelligence, 2022. DOI: [10.1148/ryai.210168](https://doi.org/10.1148/ryai.210168) | Medium-high | The map can include performance metrics, but must show subtype-specific limits and local workflow assumptions. |
| Workflow impact | Passive widget alerts and worklist flags did not meaningfully affect wait time; active reprioritization reduced queue-adjusted wait time for AI-positive ICH studies. | "Active Reprioritization of the Reading Worklist Using Artificial Intelligence Has a Beneficial Effect on the Turnaround Time for Interpretation of Head CT with Intracranial Hemorrhage," Radiology: Artificial Intelligence, 2021. DOI: [10.1148/ryai.2020200024](https://doi.org/10.1148/ryai.2020200024) | High | Buyer value depends on workflow integration, not just model accuracy. The product should map deployment pattern to measured outcomes. |
| Labeling scalability | Weakly supervised models using examination-level labels performed similarly to or better than strongly supervised models in several tests and required 35 times fewer labels. | Teneggi et al., "Examination-Level Supervision for Deep Learning-based Intracranial Hemorrhage Detection on Head CT Scans," Radiology: Artificial Intelligence, 2024. DOI: [10.1148/ryai.230159](https://doi.org/10.1148/ryai.230159); PMC: [PMC10831525](https://pmc.ncbi.nlm.nih.gov/articles/PMC10831525/) | Medium-high | RSNA can show where evidence generation may scale, while still noting that label granularity affects what can be validated. |
| Imaging-chain sensitivity | Head CT triage CNN performance can be affected by upstream acquisition, reconstruction, and preprocessing choices; CT windowing improved performance in one study. | Hooper et al., "Impact of Upstream Medical Image Processing on Downstream Performance of a Head CT Triage Neural Network," Radiology: Artificial Intelligence, 2021. DOI: [10.1148/ryai.2021200229](https://doi.org/10.1148/ryai.2021200229) | Medium | The evidence map should include site-implementation questions, not just vendor claims. Scanner protocols and preprocessing may matter. |
| Governance and reporting | RSNA AI publications and related guidance point toward structured reporting, evaluation, monitoring, and transparency expectations for AI tools. | RSNA AI evaluation and reporting guidance, including CLAIM 2024 update and broader Radiology/Radiology: AI governance articles. | Medium | The map can connect clinical evidence to governance checklists and buyer due diligence. |

## Example evidence cards

### Card 1 - Dataset provenance

**Question answered:** What data foundation exists for this clinical problem?

**Evidence:** RSNA Brain Hemorrhage CT Dataset includes 874,035 images and 25,312 CT examinations from multiple institutions and countries, annotated for five hemorrhage subtypes by neuroradiologist volunteers.

**Why it matters to a buyer:** Dataset provenance helps a governance committee ask whether a vendor's model was trained, tested, or benchmarked against data that is representative enough for the intended deployment.

**Known limitations to show, not hide:**

- Training labels were not all triple-read.
- No pixel-level annotations were included in the original dataset.
- Site-specific data discovery, de-identification, and sampling methods introduced possible bias.
- Dataset is public/noncommercial and does not substitute for local validation.

### Card 2 - Workflow value

**Question answered:** Does the AI tool change operational outcomes, or only generate another alert?

**Evidence:** In the active reprioritization study, widget-only and flag-only presentation did not significantly affect wait time. Reprioritization reduced queue-adjusted wait time for AI-positive ICH studies.

**Why it matters to a buyer:** This distinguishes "AI as detection" from "AI as workflow intervention." The deployment model is part of the product's value.

**Known limitations to show, not hide:**

- Single-institution workflow context.
- No concurrent randomized control group.
- After-hours and weekend examinations were excluded.
- Impact may vary with staffing model, queue design, PACS/RIS integration, and baseline turnaround time.

### Card 3 - Clinical performance and failure modes

**Question answered:** What performance is reported, and where does the tool struggle?

**Evidence:** A clinical workflow implementation study reported 93.0% diagnostic accuracy, 87.2% sensitivity, and 97.8% negative predictive value. Detection rates were lower for certain subtypes, including subdural hemorrhage and acute subarachnoid hemorrhage. False positives included postoperative/postischemic defects, artifacts, and tumors.

**Why it matters to a buyer:** The map should prevent "overall accuracy" from hiding safety-relevant subtype and context failures.

**Known limitations to show, not hide:**

- Report-derived ground truth may miss disagreement or latent error.
- Performance may not generalize to every institution, scanner, protocol, patient mix, or workflow.
- Negative predictive value depends on prevalence.

## Trust Passport demo fields

| Field | Example value for ICH triage POC |
|---|---|
| Intended evidence question | "What peer-reviewed evidence supports AI triage of ICH on noncontrast head CT, and what risks remain before deployment?" |
| Evidence maturity | Moderate: dataset foundation and workflow studies exist, but deployment-specific validation remains necessary. |
| Best-supported claim | "Active worklist reprioritization can reduce wait time for AI-positive ICH studies in the studied workflow." |
| Claim to avoid | "ICH AI tools are generally safe and effective across all settings." |
| Key deployment dependency | The AI output must be integrated into worklist prioritization or another operational workflow, not merely shown as a passive alert. |
| Critical limitations | Subtype performance gaps, false positives from artifacts/tumors/postoperative changes, local workflow dependence, dataset label granularity, site bias. |
| Required local validation | Compare performance and turnaround-time impact using local CT protocols, patient mix, scanner fleet, PACS/RIS workflow, staffing model, and escalation procedures. |
| Governance questions | Who sees the AI flag? Does it reorder work? How are false positives/false negatives monitored? What SOP governs critical findings? Who owns post-deployment monitoring? |

## Open evidence gaps

- Buyer willingness to pay: we have not validated that health-system buyers would pay RSNA for this packaging versus using vendor dossiers, ECRI/KLAS-style reports, or internal AI governance processes.
- Vendor coverage: this POC is about a use case, not a complete comparison of all ICH triage vendors.
- Regulatory mapping: evidence summaries would need expert review before being positioned as regulatory support.
- Updating model: a real product needs a repeatable process for keeping evidence current as new papers, FDA clearances, recalls, performance reports, and post-market data emerge.
- Liability posture: unclear how RSNA should word trust, safety, endorsement, and recommendation language.

## POC success criteria

This POC is successful if a panelist can see, in under two minutes:

1. RSNA has credible source material for at least one narrow AI use case.
2. The evidence map adds value by connecting dataset provenance, performance, workflow impact, limitations, and implementation guardrails.
3. The product should start narrow and evidence-backed, not as a broad AI marketplace or generic trust badge.

## Talk track

"We tested feasibility on one concrete wedge: intracranial hemorrhage triage on noncontrast head CT. RSNA has a large public RSNA-ASNR dataset, peer-reviewed studies on diagnostic performance and workflow impact, and papers that expose exactly the kind of limitations buyers need to understand. The POC evidence map does not say 'this AI is safe everywhere.' It says: here is what is supported, here is what depends on local workflow, here are known failure modes, and here is what a health system should validate before deployment."

