
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

## 🐛 Bug Summary

### BUG-001 — Broken URL on "Download App Now" CTA (High)
- **Location:** Privacy Policy page → Download App Now button
- **Issue:** Tapping the button results in `"This site can't be reached"` error
- **Impact:** Users cannot download the app from within the Privacy Policy page
- **Likely Cause:** Invalid URL, missing domain, or broken redirect configuration

---

### BUG-002 — Cannot Change Vote from Upvote to Downvote (High)
- **Location:** Home → Voting System (e.g., Haircut service)
- **Issue:** After selecting Upvote (Helpful), the user cannot switch to Downvote
- **Impact:** Vote is locked — users cannot correct a mistaken vote
- **Reproduced On:** Android 13, iOS 17

---

### BUG-003 — Vote Count Logic Inconsistency (High)
- **Location:** Home → All section → Any service
- **Issue:** Clicking Thumbs Down decreases Thumbs Up count by 1, but clicking Thumbs Up does NOT decrease Thumbs Down count
- **Impact:** Vote counts are inaccurate and misleading to users
- **Steps:**
  1. Click Thumbs Down → Thumbs Up shows -1 ✅
  2. Click Thumbs Up → Thumbs Down unchanged ❌

---

### BUG-004 — "Learn More" Button Not Responding on Policy Page (Medium)
- **Location:** Policy Page → Learn More button
- **Issue:** Clicking "Learn More" triggers no action — no navigation, no modal, no response
- **Impact:** Users cannot access additional information the button is supposed to provide

---

### BUG-005 — "Real Local Reports" Link Not Responding on Policy Page (Medium)
- **Location:** Policy Page → Real Local Reports link
- **Issue:** Clicking the link triggers no action whatsoever
- **Impact:** Dead link; users cannot access the Real Local Reports content

---

### BUG-006 — All Navigation Links Redirect to Wrong Page (High)
- **Location:** Policy Page → Hamburger Menu (Home, Download, FAQ)
- **Issue:** All three navigation options redirect to the same "Know Before You" page instead of their respective pages
- **Impact:** Critical navigation failure — users cannot reach Home, Download, or FAQ from the Policy page menu
- **Expected vs Actual:**

| Menu Option | Expected Destination | Actual Destination |
|---|---|---|
| Home | Home page | "Know Before You" page |
| Download | Download page | "Know Before You" page |
| FAQ | FAQ page | "Know Before You" page |

---

## ✅ Test Cases That Passed

| Test Case ID | Title |
|---|---|
| TC-PAYG-001 | Download App Now button leads to unreachable site *(bug confirmed, test executed correctly)* |
| TC-PAYG-003 | Privacy Policy page is scrollable — scrolls smoothly with no layout issues |

---

## 📄 Full Test Case Documentation

| TC ID | Title | Module | Priority | Status |
|---|---|---|---|---|
| TC-PAYG-001 | Download App Now button leads to unreachable site | Privacy Policy / Download CTA | High | FAIL (Bug) |
| TC-PAYG-002 | Unable to change vote from Upvote to Downvote | Home – Voting System | High | FAIL |
| TC-PAYG-003 | Privacy Policy page is scrollable | Privacy Policy | Medium | PASS |
| TC-PAYG-004 | Thumbs Down updates Thumbs Up count but not vice versa | Home | High | FAIL |
| TC-PAYG-005 | "Learn More" button not responding on Policy Page | Policy Page | Medium | FAIL |
| TC-PAYG-006 | "Real Local Reports" link not responding on Policy Page | Policy Page | Medium | FAIL |
| TC-PAYG-007 | Navigation links redirect to incorrect page from Policy menu | Policy Page | High | FAIL |

> Full test case details including preconditions, test data, steps to reproduce, and expected vs actual outcomes are documented in [`test-cases.xlsx`](./test-cases.xlsx) (or see the CSV below).

---

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
