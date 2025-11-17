 # End-to-End Test Automation Example with Cypress

This repository demonstrates a **robust test automation foundation** using [Cypress](https://www.cypress.io/) and GitHub Actions CI/CD, fulfilling the requirements for the Numeo AI QA/Automation Engineer take-home assessment.

---

## 🚚 Chosen Application for Automation

**Test Application:** [Sauce Demo](https://www.saucedemo.com/)  
A public sample web application used for e-commerce workflows.

---

## 📋 Table of Contents

- [About this Project](#about-this-project)
- [Architecture & Folder Structure](#architecture--folder-structure)
- [Setup Instructions](#setup-instructions)
- [Test Coverage & Approach](#test-coverage--approach)
- [Running Tests Locally](#running-tests-locally)
- [CI/CD Integration](#cicd-integration)
- [Test/Quality Strategy](#testquality-strategy)
- [Design Decisions & Trade-offs](#design-decisions--trade-offs)
- [Improvements & Onboarding](#improvements--onboarding)
- [Contact](#contact)

---

## 🔎 About this Project

- **Goal:** Showcase technical, strategic, and workflow best practices for E2E and integration testing, aligned with modern QA standards and CI/CD integration.
- **Scope:**
  - Automate critical user flows (e.g., login, shopping cart, checkout).
  - Integrate with GitHub Actions for automated validation on every commit.
  - Provide clear documentation and a practical test/quality strategy.

---

### Cypress Automation Complete E2E Framwork architecture

This framework is designed on the standards of cypress and all the directories and files are structure with proper structure. this documentation will point te files
and directories to make it understandable where to lookup of files, objects and commands.

### Framework Architecture
📦cypress\
 ┣ 📂downloads\
 ┣ 📂fixtures\
 ┃ ┗ 📜utilityData.json\
 ┣ 📂integration\
 ┃ ┗ 📂e2e\
 ┃ ┃ ┣ 📜Favorites.cy.js\
 ┃ ┃ ┣ 📜LanguageAR.cy.js\
 ┃ ┃ ┗ 📜Login.cy.js\
 ┃ ┃ ┗ 📜*.cy.js\
 ┣ 📂screenshots\
 ┣ 📂support\
 ┃ ┣ 📂pageObjects\
 ┃ ┃ ┣ 📜HomePage.js\
 ┃ ┃ ┗ 📜LoginObjects.js\
 ┃ ┃ ┗ 📜*.js\
 ┃ ┣ 📜commands.js\
 ┃ ┗ 📜e2e.js\
 ┗ 📂videos\
 ┃ ┣ 📜Favorites.js.mp4\
 ┃ ┗ 📜Login.js.mp4\
 ┣ 📜.gitignore\
 ┣ 📜cypress.config.js\
 ┣ 📜package-lock.json\
 ┣ 📜package.json

- **Tests focus on business-critical paths:**  
  ✓ User login  
  ✓ Product add-to-cart  
  ✓ Checkout flow  
  ✓ Negative login scenarios

- **Support code is modularized** for reusability and maintainability.

---

## 🛠️ Setup Instructions

**Prerequisites:**  
- [Node.js](https://nodejs.org/) (v16+ recommended)
- [npm](https://www.npmjs.com/)

**Clone & Install:**
```bash
git clone https://github.com/Amirhamza894/e2e-cypress.git
cd e2e-cypress
npm install
```

**Run E2E tests locally:**
```bash
# Run tests in headed browser
npx cypress open

# Run tests in headless mode (CI-ready)
npx cypress run
```

---

## 🚦 Test Coverage & Approach

| Feature              | Coverage Type      | Test File        |
|----------------------|-------------------|------------------|
| Login (success/fail) | E2E/Integration   | login.cy.js      |
| Add to Cart          | E2E               | cart.cy.js       |
| Checkout             | E2E               | checkout.cy.js   |
| Negative Paths       | Integration / E2E | login.cy.js      |

- **Critical, revenue-impacting flows prioritized first**
- Modular test structure for easy extension and maintenance

---

## 🤖 CI/CD Integration

### GitHub Actions

- Workflow file: [`.github/workflows/ci.yml`](.github/workflows/ci.yml)
- **Runs tests automatically** on each push and pull request
- Fails fast on test failures, providing rapid feedback to development

#### Manual Trigger

```bash
# Simulate CI locally (Unix/Mac)
npm ci
npx cypress run
```

### CI/CD Highlights

- Full repeatability and reliability
- PRs/merges must pass all tests before deployment

---

## 🛡️ Test/Quality Strategy

### 1. **Test Prioritization**
- **Automate:** Core business workflows (login, ordering, critical negative flows)
- **Manual:** Exploratory and UI/visual checks, edge cases, or non-deterministic flows

### 2. **Balance & Maintenance**
- Automate with clear ROI and stable selectors
- Review coverage quarterly; refactor or extend as product evolves

### 3. **Risk & Release Management**
- Block releases on automation failure
- Detect flaky tests and quarantine them rapidly
- Use tags/annotations for running subsets as needed

### 4. **Continuous Improvement**
- Retrospect after incidents/bugs; add or improve automated checks based on real-world defects

### 5. **Team Enablement**
- Simple, well-commented, and modular test code aids fast onboarding
- Docs and examples encourage contributions from others

---

## 💡 Design Decisions & Trade-offs

- **Cypress chosen:** Fast learning curve, excellent for modern UIs, strong local dev experience, and wide ecosystem support.
- **GitHub Actions:** Simple, robust, and mirrors professional CI/CD environments.
- **Test scope:** Focused strictly on essential flows to maximize value within tight time constraint.
- **Scalability:** Folder structure and commands easily support growth in coverage or platform targets.

---

## 🚀 Improvements & Onboarding

- **Onboarding:**  
  1. Install Node.js & npm  
  2. Run `npm install`  
  3. Try `npx cypress open` to run/debug tests interactively

- **Maintenance:**  
  - Refine selectors (use `data-*` attrs), minimize flakiness
  - Modularize test steps with custom commands
  - Expand test tags/metadata as suite grows

- **Scaling:**  
  - Support cross-browser runs (Chrome, Firefox)
  - Add parallelism and reporting integrations
  - Evolve test strategies based on defect data and business needs

---

---

**_Ready to adapt, optimize, and drive quality at scale!_**

