# Contributing to ComplyGuard-AI

Thank you for your interest in contributing to ComplyGuard-AI! This document provides guidelines and instructions for contributing to the project.

---

## Table of Contents

1. [Code of Conduct](#code-of-conduct)
2. [Getting Started](#getting-started)
3. [Contribution Types](#contribution-types)
4. [Development Workflow](#development-workflow)
5. [Commit Guidelines](#commit-guidelines)
6. [Documentation Standards](#documentation-standards)
7. [Compliance & Accuracy Requirements](#compliance--accuracy-requirements)
8. [Pull Request Process](#pull-request-process)

---

## Code of Conduct

ComplyGuard-AI is committed to providing a welcoming and inclusive environment for all contributors. We expect all participants to:

- Be respectful and inclusive
- Provide constructive feedback
- Focus on what benefits the community
- Show empathy towards other contributors
- Report unacceptable behavior to the project maintainers

---

## Getting Started

### Prerequisites

- GitHub account
- Git installed locally
- Basic familiarity with Markdown for documentation contributions
- (Optional) Access to Google AI Studio for testing Gemini 3 Pro changes

### Fork & Clone

```bash
# Fork the repository on GitHub
# Clone your fork
git clone https://github.com/YOUR_USERNAME/ComplyGuard-AI.git
cd ComplyGuard-AI

# Add upstream remote for syncing
git remote add upstream https://github.com/ArjunFrancis/ComplyGuard-AI.git
```

### Sync with Main Branch

```bash
git fetch upstream
git checkout main
git merge upstream/main
```

---

## Contribution Types

### 1. Documentation Improvements

**Examples:**
- Clarifying existing docs
- Fixing typos or broken links
- Adding examples or use cases
- Improving readability
- Translating docs to other languages (planned)

**Branch naming:** `docs/[description]`  
**Example:** `docs/clarify-compliance-framework`

### 2. Research & Analysis

**Examples:**
- Researching new compliance frameworks (NDMO, DIFC, ADGM)
- Analyzing competitive compliance tools
- Testing Gemini 3 Pro capabilities
- Validating regulatory accuracy

**Branch naming:** `research/[topic]`  
**Example:** `research/uae-compliance-frameworks`

### 3. Architecture & Design

**Examples:**
- Designing Phase 2 API structure
- Planning multimodal support (vision, audio, video)
- Designing database schema
- Planning integration with EchoLabs-AI

**Branch naming:** `design/[feature]`  
**Example:** `design/phase-2-api`

### 4. Bug Reports

**Examples:**
- Broken links in documentation
- Inaccurate compliance claims
- Mermaid diagram rendering issues
- External link failures

**How to report:**
1. Check [Issues](https://github.com/ArjunFrancis/ComplyGuard-AI/issues) to avoid duplicates
2. Create detailed issue with: title, description, steps to reproduce, expected vs actual
3. Link relevant documentation or examples

### 5. Feature Requests

**Examples:**
- New compliance frameworks
- Enhanced regulatory coverage
- New industry examples
- Tool integrations

**How to suggest:**
1. Open issue with "Feature Request" label
2. Describe the use case and expected benefit
3. Link relevant research or references
4. Propose implementation approach (if known)

---

## Development Workflow

### Branch Strategy

**Protected Branches:**
- `main` - Stable, production-ready code and docs
  - Only accepts PRs from `develop` or `docs/*` branches
  - Requires PR review before merge
  - All CI checks must pass

**Development Branches:**
- `develop` - Integration branch for Phase 2+ features
  - Can be unstable
  - Feature branches merge here first
  - Periodically merged to `main` after review

**Feature Branches:**
```
docs/[description]        # Documentation improvements
research/[topic]          # Research & analysis
design/[feature]          # Architecture & design
feature/[feature-name]    # New features (Phase 2+)
fix/[bug-description]     # Bug fixes
```

### Creating a Feature Branch

```bash
# Update main first
git checkout main
git pull upstream main

# Create feature branch
git checkout -b docs/your-enhancement

# Make changes, commit, push
git push origin docs/your-enhancement

# Create Pull Request on GitHub
```

---

## Commit Guidelines

### Commit Message Format

Follow conventional commits for clear, semantic messaging:

```
[type]: [short description]

[optional body with more details]
```

### Types

- `docs:` - Documentation changes only
- `research:` - Research additions, compliance findings
- `design:` - Architecture, design documents
- `fix:` - Bug fixes
- `feat:` - New features (Phase 2+)
- `refactor:` - Code restructuring (Phase 2+)
- `test:` - Tests (Phase 2+)
- `chore:` - Maintenance, dependency updates

### Examples

```bash
# Good
git commit -m "docs: add deployment guide for Phase 2"
git commit -m "research: validate NDMO compliance requirements"
git commit -m "docs: clarify GDPR article 15 requirements"

# Avoid
git commit -m "update stuff"
git commit -m "fixed things"
git commit -m "work in progress"
```

---

## Documentation Standards

### File Organization

```
docs/
├── README.md (if subdirectory)
├── [topic].md
└── images/
    └── [diagram].png
```

### Markdown Formatting

1. **Headers:** Use `#` for H1, `##` for H2, etc.
   ```markdown
   # Main Title (H1)
   ## Section (H2)
   ### Subsection (H3)
   ```

2. **Links:** Use relative paths for internal docs
   ```markdown
   [See Architecture](./architecture.md)
   [Visit Kaggle](https://kaggle.com)
   ```

3. **Code blocks:** Specify language for syntax highlighting
   ```markdown
   ```json
   { "example": "code" }
   ```
   ```

4. **Tables:** Use GitHub-flavored Markdown
   ```markdown
   | Column 1 | Column 2 |
   |----------|----------|
   | Value 1  | Value 2  |
   ```

5. **Lists:** Use `-` for unordered, numbers for ordered
   ```markdown
   - Item 1
   - Item 2
   
   1. First
   2. Second
   ```

### Content Standards

- **Clarity:** Use simple, clear language
- **Completeness:** Include examples where helpful
- **Accuracy:** Follow the 95% Accuracy Rule (see below)
- **Sources:** Link or cite authoritative sources
- **Consistency:** Match existing documentation style
- **Accessibility:** Include alt text for images, clear structure

### Adding New Documentation

1. **Create file** in appropriate docs/ subdirectory
2. **Add header** with title and purpose
3. **Add table of contents** for files > 500 words
4. **Include sections:** Overview, Details, Examples, References
5. **Add "Last Updated"** timestamp
6. **Update docs/INDEX.md** with link to new file
7. **Update README.md** if user-facing documentation

---

## Compliance & Accuracy Requirements

### The 95% Accuracy Rule

All compliance claims must be research-backed with **at least 95% confidence** in accuracy.

### Regulatory Sources (Priority Order)

**Tier 1 - Official Documentation (Highest Authority)**
- GDPR.eu (European Commission)
- HHS.gov / HealthCare.gov (HIPAA)
- EEOC.gov (Equal Employment Opportunity)
- SEC.gov (Securities & Exchange - SOX)
- UAE NDMO, DIFC, ADGM official portals
- ISO/IEC 42001 (AI Management Systems)
- NIST AI Risk Management Framework

**Tier 2 - Academic & Legal Sources**
- Law firm publications (specialized in privacy/AI)
- Government guidance documents
- IAPP (International Association of Privacy Professionals)
- Academic papers (arXiv, ACL, IEEE)

**Tier 3 - Industry Standards**
- OneTrust, TrustArc frameworks
- OWASP (for AI security)
- CSA AI Guidelines

### Validation Process

**Before submitting compliance-related changes:**

1. **Identify the claim:** What regulatory requirement are you documenting?
2. **Find Tier 1 source:** Check official government/standards documents
3. **Document source:** Include URL and specific section/article number
4. **Note confidence:** If < 95% certain, add disclaimer: *"Based on available research, X appears to align with [regulation], but legal review is recommended because..."*
5. **Include alternatives:** If uncertain, provide multiple interpretations with pros/cons

### Example: Good Compliance Documentation

```markdown
## GDPR - Right to Erasure (Article 17)

**Requirement:** Individuals have the right to erasure in certain circumstances.

**Key Points:**
- Must erase within 1 month of request
- Exceptions: Legal obligations, public interest, freedom of expression
- **Source:** [GDPR Article 17 - EC Official](https://gdpr-info.eu/art-17-gdpr/)
- **Confidence Level:** 98% (Direct from official regulation)

**ComplyGuard Detection:** 
If AI agent denies erasure without valid exception, score reduced by X points.
```

### What to Avoid

❌ Making up compliance requirements  
❌ Citing sources you haven't read  
❌ Using non-authoritative sources without triangulation  
❌ Making legal interpretations without disclaimers  
❌ Outdated information without verification  

---

## Pull Request Process

### Before Submitting

1. **Sync with latest:** `git pull upstream main`
2. **Test locally:** Read through all changes
3. **Check links:** Verify all internal/external links work
4. **Validate compliance claims:** Apply 95% accuracy rule
5. **Review tone:** Ensure consistent with existing docs

### Submitting a PR

1. **Go to GitHub** and click "New Pull Request"
2. **Select branches:** Compare `your-fork:docs/your-feature` → `upstream:main`
3. **Fill PR template:**
   ```markdown
   ## Description
   Brief summary of changes
   
   ## Type of Change
   - [ ] Documentation improvement
   - [ ] Research/analysis
   - [ ] Architecture/design
   - [ ] Bug fix
   - [ ] Feature request
   
   ## Related Issues
   Closes #[issue number]
   
   ## Changes Made
   - Change 1
   - Change 2
   
   ## Sources (if compliance-related)
   - [Source 1](url)
   - [Source 2](url)
   
   ## Testing
   - [x] Verified links work
   - [x] Checked spelling/grammar
   - [x] Validated compliance claims
   ```

4. **Create PR** and request review

### PR Review Process

**Reviewers will check:**
- ✅ Clarity and completeness
- ✅ Accuracy (especially compliance claims)
- ✅ Style consistency
- ✅ Broken links or formatting issues
- ✅ Alignment with project goals

**Approval process:**
- At least 1 maintainer approval required for `docs/` branches
- At least 2 approvals for `feature/` or `research/` branches
- All CI checks must pass

### After Merge

1. **Delete branch:** GitHub will prompt you
2. **Celebrate:** Your contribution is live! 🎉
3. **Update local:** `git pull upstream main`

---

## Common Questions

**Q: Can I contribute code to the live AI Studio app?**  
A: Not yet. Phase 2 (Q1 2026) will allow API and dashboard contributions. For now, documentation and research contributions are welcome.

**Q: How do I report security issues?**  
A: Please email security concerns to the maintainers privately. Do not open public issues for security vulnerabilities.

**Q: What if I'm not sure about regulatory accuracy?**  
A: That's okay! Submit your PR with a note in the description requesting verification. Mark uncertain claims with disclaimers.

**Q: Can I propose a new compliance framework?**  
A: Absolutely! Open an issue describing why it's important (market demand, regulatory requirement, use cases). Include research sources.

**Q: How long does PR review take?**  
A: Usually 3-5 business days. Complex PRs may take longer.

---

## Getting Help

- **Questions?** Open a [GitHub Discussion](https://github.com/ArjunFrancis/ComplyGuard-AI/discussions)
- **Report bugs?** Create an [Issue](https://github.com/ArjunFrancis/ComplyGuard-AI/issues)
- **Email?** Contact through repository

---

## Recognition

Contributors will be recognized in:
- Repository `CONTRIBUTORS.md` file
- Release notes
- Project README (for significant contributions)
- Monthly contributor spotlight (TBA)

---

**Thank you for contributing to ComplyGuard-AI! Together, we're preventing AI lawsuits. 🛡️**

*Last Updated: December 20, 2025*
