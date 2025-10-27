# 🧩 Group Test Management Report  
## *Word Puzzle Game Plus*  

---

### 👥 Team Members

| Role | Name | Responsibility |
|------|------|----------------|
| **Test Manager** | Edwin Kariuki | Test plan, scheduling, monitoring, metrics |
| **Risk Analyst** | Victor Mutinda | Risk identification, assessment, prioritization |
| **Test Executor** | Rehema Shammah | Test case execution, defect reporting, validation |

---

## 🧭 Section 1: Test Plan  
**Role:** Test Manager — *Edwin Kariuki*

### 🎯 Objectives
The purpose of this test plan is to define the strategy, scope, resources, and schedule for testing the **Word Puzzle Game Plus**.  
Focus areas include:

- Correct functionality of **Reset**, **Leaderboard**, and **Bonus Round**.  
- Data integrity of **localStorage**.  
- Validation of **risk-based testing** and **metric-driven quality monitoring**.

---

### 📦 Scope

#### ✅ In-Scope
- Functional testing of gameplay logic.  
- UI/UX behavior and state transitions.  
- LocalStorage persistence and data validation.  
- Regression testing for Reset, Bonus, and Leaderboard functions.

#### ❌ Out-of-Scope
- Non-Chromium browsers.  
- Backend or network latency behavior (offline app).  
- Performance or load tests.

---

### 👥 Roles and Resources

| Role | Member | Tool / Resource |
|------|---------|----------------|
| Test Manager | Edwin Kariuki | Google Sheets, GitHub Projects |
| Risk Analyst | Victor Mutinda | Excel, Risk Matrix |
| Test Executor | Rehema Shammah | Chrome Browser, Microsoft Edge, GitHub Issues |

---

### 🗓️ Schedule

| Phase | Duration | Deliverable |
|--------|-----------|-------------|
| Planning | Day 1–2 | Test Plan & Risk Matrix |
| Test Design | Day 3–4 | 8+ Test Cases |
| Execution | Day 5–6 | Logs & Defect Reports |
| Reporting | Day 7 | Metrics & Reflection |

---

### 🚦 Entry / Exit Criteria

**Entry Criteria:**
- Application accessible in Chrome.  
- Word list loads without console errors.  
- GitHub issue board configured.  

**Exit Criteria:**
- 100% of high/medium risk cases executed.  
- Pass rate ≥ 85%.  
- Critical defects resolved or deferred.  

---

### 💻 Environment

| Component | Version |
|------------|----------|
| OS | Windows 10+ |
| Browser | Chrome 120+ |
| Storage | localStorage enabled |
| Network | Offline |

---

### 📊 Monitoring Metrics

| Metric | Formula | Target |
|---------|----------|---------|
| Pass Rate | (Passed ÷ Total) × 100 | ≥ 85% |
| Defect Density | Defects ÷ Test Cases | ≤ 0.25 |
| Risk Coverage | (Tested Risks ÷ Total) × 100 | ≥ 80% |
| Regression Rate | (Passed Regression ÷ Total Regression) × 100 | ≥ 90% |

---

## ⚠️ Section 2: Risk Analysis  
**Role:** Risk Analyst — *Victor Mutinda*

### 🎯 Purpose
Identify, assess, and prioritize potential risks using a **Likelihood × Impact** model (scale 1–5).

---

### 🧮 Risk Register

| ID | Risk Description | Type | L | I | Exposure | Priority | Mitigation |
|----|------------------|------|---|---|-----------|-----------|-------------|
| R1 | Leaderboard fails to persist scores | Functional | 4 | 5 | 20 | High | Validate JSON; test persistence after reset |
| R2 | Bonus round triggers incorrectly | Functional | 3 | 5 | 15 | High | Validate modulo logic; simulate multiple rounds |
| R3 | Reset fails to clear state | Functional | 4 | 4 | 16 | High | Verify all variables reset |
| R4 | Accessibility issue for screen readers | UX | 3 | 3 | 9 | Medium | Validate `aria-label`, keyboard flow |
| R5 | Leaderboard sorting incorrect | Functional | 3 | 4 | 12 | Medium | Test multiple scores; check descending order |
| R6 | Hint deduction repeated | Functional | 3 | 4 | 12 | Medium | Verify deduction happens once |
| R7 | State lost on tab close | Non-Functional | 2 | 3 | 6 | Low | Validate session persistence |

---

### 📊 Risk Exposure Summary

| Priority | Count | Example Risks |
|-----------|--------|----------------|
| High | 3 | R1, R2, R3 |
| Medium | 3 | R4, R5, R6 |
| Low | 1 | R7 |

---

### 🥧 Risk Coverage Plan
- **High (R1–R3):** 50% of total testing effort  
- **Medium (R4–R6):** 40%  
- **Low (R7):** 10%

```
🟩 High – 50%
🟨 Medium – 40%
⬜ Low – 10%
```

---

## 🧪 Section 3: Test Design & Execution  
**Role:** Test Executor — *Rehema Shammah*

### 🎯 Objective
To execute structured test cases mapped to identified risks and ensure system behavior matches expected functionality.

---

### 🧩 Test Case Summary

| ID | Feature | Risk | Type | Status |
|----|----------|------|------|---------|
| TC-01 | Reset Game | R3 | Functional | ✅ |
| TC-02 | Leaderboard Persistence | R1 | Functional | ⚠️ |
| TC-03 | Bonus Round Logic | R2 | Functional | ✅ |
| TC-04 | Leaderboard Sorting | R5 | Functional | ✅ |
| TC-05 | Hint Deduction | R6 | Functional | ✅ |
| TC-06 | Empty Guess | — | Negative | ✅ |
| TC-07 | Malformed LocalStorage | R1 | Negative | ✅ |
| TC-08 | Accessibility | R4 | Usability | ✅ |

---

### 📊 Test Results Summary

| Metric | Value |
|---------|--------|
| Pass Rate | 87.5% |
| Defect Density | 0.125 |
| Risk Coverage | 85.7% |
| Regression Rate | 90% |

---

## 🐞 Section 4: Defect Reporting  
**Role:** Test Executor — *Rehema Shammah*

### 🧾 Summary Table

| ID | Title | Severity | Risk | Status |
|----|--------|-----------|--------|--------|
| D1 | Leaderboard not updating | High | R1 | Open |
| D2 | Hint message overlap | Medium | R6 | Closed |
| D3 | Reset focus missing | Minor | R3 | Closed |

---

### 🧩 Detailed Defects

#### **D1 — Leaderboard not updating after first solve**
- **Severity:** High  
- **Risk:** R1  
- **Steps:** Solve 1st puzzle → Check leaderboard → Refresh → Score missing  
- **Expected:** Score appears immediately and persists  
- **Actual:** Score missing until second solve  
- **Status:** Open  
- **Fix Suggestion:** Call `updateLeaderboard()` earlier in solve sequence  

---

#### **D2 — Hint message overlaps success message**
- **Severity:** Medium  
- **Risk:** R6  
- **Expected:** Only one active message  
- **Actual:** “Hint shown” overlaps with “Correct!” text  
- **Status:** Closed  

---

#### **D3 — Reset does not restore input focus**
- **Severity:** Minor  
- **Risk:** R3  
- **Expected:** Input field refocused after reset  
- **Actual:** Focus lost, requires manual click  
- **Status:** Closed  

---

## 📈 Section 5: Test Monitoring & Metrics  
**Role:** Test Manager — *Edwin Kariuki*

### 📊 Key Metrics Dashboard

| Metric | Formula | Result |
|---------|----------|---------|
| **Pass Rate** | (7 ÷ 8) × 100 | **87.5%** |
| **Defect Density** | 3 ÷ 8 | **0.375** |
| **Risk Coverage** | (6 ÷ 7) × 100 | **85.7%** |
| **Regression Success Rate** | (9 ÷ 10) × 100 | **90%** |

---

### 📈 Test Progress Table

| Date | Total Tests | Executed | Passed | Failed | Defects Logged |
|------|--------------|-----------|--------|--------|----------------|
| Day 1 | 0 | 0 | 0 | 0 | 0 |
| Day 3 | 5 | 5 | 4 | 1 | 1 |
| Day 5 | 8 | 8 | 7 | 1 | 3 |

---

### 📊 Visualization Suggestions

```
📊 Pie Chart: Test Outcomes
🟩 Passed – 87.5%
🟥 Failed – 12.5%

📈 Bar Graph: Risk Coverage
High – 100%
Medium – 83%
Low – 100%
```

---

### 🧠 Analysis
- High-risk coverage achieved as planned (≥80%).  
- Most defects in first cycle were related to **Leaderboard** functionality.  
- Regression tests stable after minor fixes.  
- Metrics show controlled defect discovery with manageable density.

---

## 💬 Section 6: Reflection  
**All Roles**

### 🧩 Lessons Learned

| Area | Reflection |
|-------|-------------|
| **Risk-Based Approach** | Identifying risk exposure early focused testing on leaderboard and reset functions, preventing major post-release bugs. |
| **Collaboration** | GitHub Issues improved traceability of responsibilities and accountability among roles. |
| **Trade-offs** | Achieving deep coverage on high-risk areas required skipping low-impact UI combinations. |
| **Metrics Insight** | Pass rate (87.5%) and risk coverage (85.7%) indicated a balanced trade-off between depth and speed. |

---

### 💡 Recommendations
- Automate leaderboard tests using browser-based scripts.  
- Add accessibility testing with tools like AXE.  
- Include mobile Chrome validation in next iteration.  

---

### ✅ Conclusion
The *Word Puzzle Game Plus* testing cycle met the project’s key objectives:
- High coverage on core risks  
- Controlled defect rate  
- Evidence-based monitoring  

> *“Quality was achieved not by finding all bugs, but by testing where it mattered most.”*
