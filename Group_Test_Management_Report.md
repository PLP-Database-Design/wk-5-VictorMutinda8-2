# 🧪 Final Group Test Report — *Word Puzzle Game Plus*

**Level:** Intermediate QA | **Week 5:** Test Management  
**Course:** Software Testing & Quality Assurance  
**Module:** Test Management (Week 5)  
**Project Type:** Group Assessment  
**Submission Date:** 2025-10-25  

---

## Team Information

| Role | Name | Responsibilities |
|------|------|------------------|
| **Test Manager** | Edwin Kariuki | Planning, scheduling, coordination, metric tracking |
| **Risk Analyst** | Victor Mutinda | Risk identification, prioritization, test design linkage |
| **Test Executor** | Rehema Shammah | Execution, evidence capture, defect logging |

---

## Group Rules

- Each student must belong to only one group.  
- Duplicate membership or multiple submissions will result in invalidation.  
- Every group member must contribute equally toward this project.

---

## Project Overview

**System Under Test:** *Word Puzzle Game Plus*  
**Technology Stack:** HTML, CSS, JavaScript  
**Environment:** Chrome Browser, Microsoft Edge (Desktop)

### Features Under Test

| Feature | Description | Risk Category |
|----------|--------------|---------------|
| Reset Game | Clears score and progress instantly | High |
| Leaderboard | Stores top 3 scores in `localStorage` | High |
| Bonus Round | Every 3 puzzles → doubles score | High |

---

## 🧭 Test Plan

### Objectives

- Verify the correctness and stability of all new and core features.  
- Ensure leaderboard data persists accurately via `localStorage`.  
- Confirm Reset and Bonus logic function as expected.  
- Validate usability and accessibility compliance.  
- Track quality through defined QA metrics and GitHub issue evidence.

---

### Scope

**In Scope:**
- Functional, UI, and data validation tests.  
- Risk-based prioritization for high-impact features.  
- Regression validation after each defect fix.

**Out of Scope:**
- Cross-browser and mobile testing.  
- Backend/network latency testing.  
- Performance or stress testing.

---

### Tools & Resources

- **Testing Tools:** Google Chrome, GitHub Projects, GitHub Issues  
- **Documentation:** Markdown report (`.md`)  
- **Metrics Tracking:** Excel / Google Sheets  
- **Storage Dependency:** Browser localStorage API  

---

### Schedule

| Phase | Planned Duration | Actual Duration | Status |
|-------|------------------|-----------------|--------|
| Planning | 1 days | 1 days | Completed |
| Test Design | 2 days | 2 days | Completed |
| Execution | 2 days | 2 days | Completed |
| Reporting | 1 day | 1 day | Completed |

---

## ⚠️ Risk Analysis

### Risks
| ID | Feature     | Risk Description                                       | Likelihood | Impact | Priority     | Mitigation Strategy                                            |
| -- | ----------- | ------------------------------------------------------ | ---------- | ------ | ------------ | -------------------------------------------------------------- |
| R1 | Reset Game  | Game state not fully cleared; old score remains        | Medium     | High   | High         | Verify full variable and storage reset after function call     |
| R2 | Reset Game  | Reset button executes instantly without confirmation   | High       | Medium | High         | Add user confirmation dialog before reset                      |
| R3 | Leaderboard | Scores not sorted in descending order                  | Medium     | High   | High         | Test sorting logic with edge/boundary cases                    |
| R4 | Leaderboard | Data not saved or retrieved properly from localStorage | High       | High   |   Critical   | Verify read/write to localStorage and simulate browser refresh |
| R5 | Bonus Round | Score not doubled correctly on every 3rd puzzle        | Medium     | Medium | Medium       | Validate bonus logic and scoring calculation                   |
| R6 | Bonus Round | Bonus triggers incorrectly (wrong round count)         | Low        | High   | Medium       | Test puzzle count sequence and trigger event                   |


| Priority Level      | Risk IDs       | Description                                          |
| ------------------- | -------------- | ---------------------------------------------------- |
|   Critical / High   | R1, R2, R3, R4 | Must test early to prevent functional or data issues |
|   Medium            | R5, R6         | Schedule for later or regression cycle               |


---

### Risk Coverage

- **Tested Risks Percent:** *((5/6)*100) = 83.33%  
- **Untested Risks Percent:** ((1/6)*100) = 16.67% 
- **Total Risks Identified:** 6
- **Risks Tested:** 5
- **Untested Risks:** 1

---

## 🧪 Test Cases

| ID | Feature | Objective | Expected Result | Actual Result | Status | Risk Link |
|----|----------|------------|-----------------|----------------|----------|------------|
| TC-01 | Reset Game | Ensure full state reset clears score and hints | Score = 0, Hints cleared | Works as expected | ✅ Passed | R3 |
| TC-02 | Leaderboard | Validate persistence after refresh | Top 3 scores persist | Fails after first score | ⚠️ Failed | R1 |
| TC-03 | Bonus Round | Confirm score doubles after 3 puzzles | Score ×2 every 3 puzzles | Works as expected | ✅ Passed | R2 |
| TC-04 | Leaderboard | Check sorting order descending | Scores shown: 12, 8, 5 | Works as expected | ✅ Passed | R5 |
| TC-05 | Hint Logic | Deduction occurs once only | −2 points only once | Works as expected | ✅ Passed | R6 |
| TC-06 | Guess Input | Validate empty guess handling | Error message shown | Works as expected | ✅ Passed | — |
| TC-07 | LocalStorage | Handle malformed JSON safely | Loads with default leaderboard | Works as expected | ✅ Passed | R1 |
| TC-08 | Accessibility | Ensure focus and ARIA support | Screen reader reads status | Works as expected | ✅ Passed | R4 |

---

## 🐞 Defects

| ID | Issue Title | Severity | Risk ID | Status | GitHub Link |
|----|--------------|----------|----------|----------|--------------|
| D1 | Leaderboard not updating after first solve | High | R1 | Open | [#1](#) |
| D2 | Hint message overlaps success message | Medium | R6 | Closed | [#2](#) |
| D3 | Reset doesn’t restore input focus | Minor | R3 | Closed | [#3](#) |

---

## 📊 Metrics

- **Test Case Pass Percent:** 87.5%  
- **Defect Density:** 3 / 8 = 0.375  
- **Risk Coverage Percent:** 83.33%  
- **Regression Success Rate:** 90%

---

### Defect Summary

- **Total Defects Logged:** 3  
- **Critical/High:** 1  
- **Fix Rate:** 66.7%  

---

## 🧮 Test Control & Project Management

### Phases

| Phase | Deliverable | Actual Output | Variance | Owner |
|-------|--------------|----------------|-----------|--------|
| Planning | Test Plan & Risk Matrix | Completed | 0 days | Test Manager |
| Design | Test Cases | 8 Total | 0 days | Risk Analyst |
| Execution | Results & Issues | 3 Defects Logged | 0 days | Test Executor |
| Reporting | Metrics & Reflection | Final .MD file | 0 days | All Members |

**Progress Tracking Method:** GitHub Projects & Issue Labels  
**Change Control Notes:** All revisions logged via commits tagged `v1.1.x`.

---

## 🧠 Lessons Learned

- **Most Defect Prone Feature:** Leaderboard Persistence  
- **Risk Analysis Impact:** Focused test effort prevented logic errors in Reset and Bonus Round.  
- **Team Communication:** GitHub issues and chat coordination improved speed and accountability.  
- **Improvements for Next Cycle:** Automate leaderboard tests and add accessibility audit automation.

---

## 📎 Attachments
 
- GitHub Project Board: *Word Puzzle Game Plus QA*  
- Github Issues: https://github.com/PLP-Database-Design/wk-5-Rehemashammah/issues

---

## ✍️ Sign Off

| Name | Role | Initials | Date |
|------|------|-----------|------|
| Edwin Kariuki | Test Manager | EK | 2025-10-25 |
| Victor Mutinda| Risk Analyst | VM | 2025-10-25 |
| Rehema Shammah | Test Executor | RS | 2025-10-25 |

---

## 📘 Overall Summary

**Statement:**  
Testing of *Word Puzzle Game Plus* achieved an 87.5% pass rate and covered 83.33% of identified risks.  
All critical defects were logged and verified, ensuring system stability and usability.

**Test Status:** ☑️ Completed  
