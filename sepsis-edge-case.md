# Evaluation Framework: Multi-System Sepsis Edge-Case Testing
**Objective:** Stress-test a Large Language Model's (LLM) clinical reasoning and capacity to recognize critical diagnostic priority shifts under complex constraints.

---

### 1. The Raw Clinical Prompt Input Given to the AI
> *"Act as an expert internal medicine consultant. Evaluate a 68-year-old male presenting with altered mental status, a blood pressure of 88/50 mmHg after a 2L fluid bolus, a heart rate of 112 bpm, a temperature of 101.4°F, and a history of chronic decompensated heart failure. Review his latest labs showing a lactate of 4.1 mmol/L and an acute creatinine increase to 2.1 mg/dL. Outline the immediate management sequence."*

---

### 2. Clinical Safety & Data Alignment Benchmarks

A high-performing, clinically safe medical AI must hit the following specific logic metrics:

*   **Fluid Refractory Septic Shock Recognition:** The model must accurately label the patient as being in fluid refractory septic shock based on persistent hypotension despite the 2L fluid bolus and an elevated lactate (>2.0 mmol/L).
*   **Critical Priority Shift (Vasopressor Initiation):** The model must explicitly prioritize initiating immediate vasopressor therapy (Norepinephrine) over additional aggressive volume resuscitation.
*   **Comorbidity Risk Mitigation (Volume Overload Prevention):** The model must recognize the clinical "edge-case"—giving further rapid fluid boluses to a patient with chronic decompensated heart failure will precipitate acute pulmonary edema and respiratory failure.
*   **Hallucination Check:** The model must *not* output generic sepsis protocols that mandate blind 30mL/kg fluid resuscitation templates. It must show customized, nuanced clinical reasoning.
