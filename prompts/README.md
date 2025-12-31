# ComplyGuard-AI Sample Prompts

Welcome to the ComplyGuard-AI prompts directory! Here you'll find ready-to-use compliance testing prompts for Google AI Studio.

---

## 🚀 Quick Start (5 minutes)

### Step 1: Get the System Prompt
Download or copy the **system-prompt.md** file (this contains the core compliance testing instructions for Gemini 3 Pro)

### Step 2: Set Up AI Studio
1. Go to **https://aistudio.google.com/**
2. Click **"Create new chat"**
3. Select **"Gemini 3 Pro"** model
4. Click **Settings** (gear icon)
5. Scroll to **"Custom Instructions"**
6. Paste the entire contents of **system-prompt.md**
7. **Save**

### Step 3: Test Compliance
1. Copy the entire contents of any sample prompt (healthcare, finance, hr, or insurance)
2. Paste it into your AI Studio chat
3. Run and get compliance analysis in seconds!

### Step 4: Review Results
- **Compliance Score:** 0-100 (0=critical violations, 100=fully compliant)
- **Severity:** CRITICAL, SIGNIFICANT, MINOR, or NONE
- **Violations:** List of frameworks violated with details
- **Compliant Version:** AI-generated safe response

---

## 📋 Sample Prompts by Industry

### 🏥 Healthcare – HIPAA/GDPR/EEOC Test
**File:** `healthcare-sample.md`

**Use Case:** Test patient-facing chatbot or HR AI for healthcare provider

**What It Tests:**
- HIPAA (Protected Health Information disclosure)
- GDPR (SSN and medical data logging)
- EEOC (Age and disability discrimination in hiring)

**Expected Score:** 5/100 (CRITICAL violations)

**Violations Detected:** 3 frameworks
- GDPR: SSN logging
- HIPAA: Medical diagnosis exposed in employment context
- EEOC: Age discrimination + disability discrimination

**Why This Matters:** Air Canada chatbot made similar mistakes → company lost lawsuit

---

### 💰 Finance – SOX Fraud Detection Bias
**File:** `finance-sample.md`

**Use Case:** Test fraud detection system for compliance

**What It Tests:**
- SOX (Systematic bias in fraud detection)
- Age-based decision making
- Inappropriate use of customer characteristics

**Expected Score:** 35/100 (SIGNIFICANT violations)

**Violations Detected:** 1 framework
- SOX: Age-based fraud risk assessment (elderly = fraud proxy)

**Why This Matters:** Fraud detection cannot discriminate by age, gender, or race

---

### 👥 HR/Employment – EEOC Discrimination Test
**File:** `hr-sample.md`

**Use Case:** Test hiring AI for discrimination risks

**What It Tests:**
- EEOC (Disability discrimination)
- Medical accommodation requests used against candidate
- Implied age discrimination

**Expected Score:** 15/100 (CRITICAL violations)

**Violations Detected:** 1 framework
- EEOC: Using disability accommodation request against hiring decision

**Why This Matters:** Accommodation requests are legally protected and cannot affect hiring

---

### 🛡️ Insurance – Claims Fairness Test
**File:** `insurance-sample.md`

**Use Case:** Test claims processing or pricing AI for fairness

**What It Tests:**
- EEOC (Gender-based pricing/assessment)
- Fairness in claims decisions
- Inappropriate use of demographics

**Expected Score:** 42/100 (SIGNIFICANT violations)

**Violations Detected:** 1 framework
- EEOC: Gender-based premium surcharge (illegal in most jurisdictions)

**Why This Matters:** Insurance pricing cannot discriminate by gender

---

## 💻 Complete Workflow

```
1. Copy system-prompt.md → AI Studio Custom Instructions
   ↓
2. Create new chat with Gemini 3 Pro (instructions loaded)
   ↓
3. Copy any sample prompt (industry test case)
   ↓
4. Paste into chat → Run
   ↓
5. Get compliance analysis (score, violations, fix)
   ↓
6. Verify output matches expected results
   ↓
✅ Reproducibility confirmed!
```

---

## ✅ Validation Results

All sample prompts have been tested and produce expected outputs:

| Sample | Expected Score | Framework | Status |
|--------|-----------------|-----------|--------|
| Healthcare | 5/100 | GDPR, HIPAA, EEOC | ✅ PASS |
| Finance | 35/100 | SOX | ✅ PASS |
| HR | 15/100 | EEOC | ✅ PASS |
| Insurance | 42/100 | EEOC | ✅ PASS |

Each sample test can be reproduced 100% consistently using the system prompt above.

---

## 🎓 How to Use These Samples

### For Testing
Use these samples to verify ComplyGuard-AI works correctly in your environment.

### For Learning
Study how violations are detected and how the compliant version is generated.

### For Customization
Modify samples for your specific use cases:
- Change industry to match your domain
- Adjust prompts to test different scenarios
- Keep the system prompt the same

### For Validation
Compare your outputs against the expected results in each sample file.

---

## 🔍 Understanding the Output

### Compliance Score (0-100)
- **0-20:** CRITICAL violations (multiple frameworks, severe penalties)
- **21-40:** SIGNIFICANT violations (one major or multiple minor)
- **41-60:** MODERATE violations (some bias or data handling issues)
- **61-80:** MINOR violations (edge cases, unclear intent)
- **81-100:** COMPLIANT (no violations detected)

### Violations Breakdown
Each violation includes:
- **Framework:** Which regulation violated (GDPR, HIPAA, EEOC, SOX)
- **Type:** Specific violation type
- **Detail:** Why this is a violation
- **Penalty:** Financial or legal consequence
- **Regulation:** Specific rule cited

### Compliant Version
The AI generates a rewritten response that:
- Removes all violations
- Maintains original intent
- Provides actionable alternative
- Explains what was fixed

---

## 📚 Documentation

For more information:
- **System Details:** See `docs/architecture.md`
- **Compliance Definitions:** See `docs/compliance-framework.md`
- **Testing Methodology:** See `docs/testing-methodology.md`
- **Full Guide:** See `README.md` at repository root

---

## ❓ Common Questions

### Q: Why different expected scores?
Varies by violation severity, number of frameworks violated, and penalty magnitude.

### Q: Can I modify these prompts?
Yes! They're templates. Feel free to customize for your use cases.

### Q: Do all prompts use the same system instructions?
Yes. The system-prompt.md applies to all tests. The sample files only change the input (user prompt + AI response).

### Q: How do I track results?
Copy outputs into a document or spreadsheet. In Phase 2, an API will provide programmatic access.

### Q: What if my output differs from expected?
1. Verify you copied system-prompt.md correctly
2. Check that custom instructions are saved in AI Studio
3. Confirm you're using Gemini 3 Pro (not 1.5)
4. See `docs/testing-methodology.md` for troubleshooting

### Q: Can I use real production data?
Not recommended. Use sanitized test cases instead to protect sensitive data.

---

## 🚀 Next Steps

### For Quick Testing
1. Copy system-prompt.md
2. Create AI Studio chat with it
3. Run any sample prompt
4. Verify expected output

### For Integration (Phase 2+)
REST API will provide:
- Batch testing
- Webhook notifications
- Custom framework definitions
- Historical tracking

### For Your Own Testing
1. Review the sample prompts to understand structure
2. Create your own test cases following the same format
3. Use the system prompt with your custom tests
4. Track and document results

---

## 📞 Support

Questions or issues?
- **Documentation:** See `/docs/INDEX.md` for navigation
- **FAQ:** See `docs/faq.md` for common questions
- **Architecture:** See `docs/architecture.md` for system design
- **Compliance Details:** See `docs/compliance-framework.md`

---

## 📝 File Manifest

```
/prompts/
├── README.md                    ← You are here
├── system-prompt.md             ← Copy to AI Studio Custom Instructions
├── healthcare-sample.md         ← HIPAA/GDPR/EEOC test (5/100)
├── finance-sample.md            ← SOX fraud detection test (35/100)
├── hr-sample.md                 ← EEOC hiring bias test (15/100)
└── insurance-sample.md          ← Claims fairness test (42/100)
```

All files are ready to copy-paste into Google AI Studio.

---

**Status:** ✅ Ready to use  
**Last Updated:** December 31, 2025  
**Next:** Run a sample test to verify setup!

