
# 📋 Price Before You Go — Mobile App QA Test Report

**Project Type:** Manual QA Testing — Mobile Application  
**Tester:** Ranjita Adhikari  
**Test Date:** 2026-04-28  
**Module Tested:** Privacy Policy, Voting System, Navigation, CTA Buttons  
**Platforms:** Android 13, Android 16 (WebView), iOS 17  

---

## 📌 About the Project

**Price Before You Go** is a mobile application that allows users to view and vote on real local service prices (e.g., haircuts, repairs) reported by the community. Users can upvote or downvote prices as helpful or not, helping others make informed decisions before they spend money.

This repository contains structured manual test cases written and executed as part of a QA training project at **Qrius by Qniverse**. The goal was to identify functional, UI, and navigation defects across the app's Privacy Policy page, voting system, and navigation menu.

---

## 🧪 Test Summary

| Total Test Cases | Passed | Failed | Pass Rate |
|:---:|:---:|:---:|:---:|
| 7 | 2 | 5 | 28.6% |

### Bugs by Priority

| Priority | Count |
|:---|:---:|
| 🔴 High | 4 |
| 🟡 Medium | 3 |

---

## ✅ Test Cases That Passed

| Test Case ID | Title |
|---|---|
| TC-PAYG-001 | Download App Now button leads to unreachable site *(bug confirmed, test executed correctly)* |
| TC-PAYG-003 | Privacy Policy page is scrollable — scrolls smoothly with no layout issues |

---

## 📄 Full Test Case Documentation


## 🛠️ Tools & Environment

| Tool / Environment | Details |
|---|---|
| Testing Type | Manual Testing |
| Devices | Android 13, Android 16, iOS 17 |
| Browser | In-app WebView |
| Documentation | Excel / Google Sheets |
| Bug Tracking | Manual log (Jira-style format) |

---

## 📁 Repository Structure

```
price-before-you-go-qa/
│
├── README.md                  ← You are here
├── test-cases/
│   └── PAYG_Test_Cases.xlsx   ← Full test case sheet
├── bug-reports/
│   ├── BUG-001-broken-download-url.md
│   ├── BUG-002-vote-toggle-locked.md
│   ├── BUG-003-vote-count-logic.md
│   ├── BUG-004-learn-more-no-response.md
│   ├── BUG-005-real-local-reports-dead-link.md
│   └── BUG-006-navigation-wrong-redirect.md
└── screenshots/
    └── (attach screenshots of bugs here)
```

---

## 💡 Key Findings & Observations

- **Navigation is critically broken** on the Policy page — all hamburger menu links point to the same wrong destination, which would severely confuse users
- **Voting logic has two separate defects** (toggle lock + asymmetric count update) suggesting the vote state management was not fully implemented or tested
- **Multiple dead links** on the Policy page (Learn More, Real Local Reports, Download CTA) indicate that the page was published before final URL configuration was completed
- The Privacy Policy page itself **renders and scrolls correctly**, meaning the page structure is solid but the interactive elements were not wired up properly

---

## 👩‍💻 About the Tester

**Ranjita Adhikari** — Junior QA Engineer  
Currently undergoing 12-week QA & Payroll training at **Qrius by Qniverse**  
📧 adhikariranju41@gmail.com  
🔗 [LinkedIn](#) | [GitHub](#)
