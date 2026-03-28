# PCI DSS Gap Assessment – Ikigai E-commerce Services Limited

*This project reflects the type of work I support in real-world engagements. The documentation uses synthetic data; no client information is reproduced, and the templates are either self-developed or sourced from open-source resources.*

---

Supported a PCI DSS gap [assessment](https://drive.google.com/drive/folders/1BfAAtvKAkp5tkcBksxKAHdXZVYGDtdQS?usp=sharing) for an e-commerce merchant processing approximately 50,000 annual transactions through a fully outsourced payment model via Paystack. Because customers are redirected to Paystack's PCI‑validated environment, Ikigai's internal systems never store, process, or transmit cardholder data, qualifying them for SAQ A.

Accordingly, this assessment focused exclusively on the two SAQ A requirements applicable to Ikigai’s corporate systems: *Requirement 8 (Access Control) and Requirement 10 (Logging & Monitoring)*, as platforms such as Google Workspace and the admin panel support e-commerce operations.

The review evaluated these controls against PCI DSS v4.0.1 to assess readiness for SAQ A submission and validate the effectiveness of the outsourced payment model.

---

## Approach
*   Administered a structured **[PCI DSS Scoping Questions Checklist](https://docs.google.com/spreadsheets/d/1pZOHwVT5B98Fn49eIUqa1bYRUD_M2gdP/edit?usp=drive_link&ouid=101134501969411208830&rtpof=true&sd=true)** to confirm SAQ A eligibility, map data flows, and identify in-scope systems based on the fully outsourced payment model.
  
*   Generated a comprehensive **[Pre-QSA Readiness Evidence Pack](https://docs.google.com/document/d/1-BbNHY4Lvf9mpz-V0oVK0RKhORUlfce4/edit?usp=sharing&ouid=101134501969411208830&rtpof=true&sd=true)** to map existing controls against PCI DSS requirements and track evidence collection across policies, technical configurations, and vendor documentation.
  
*   Performed evidence-based testing documented in the **[PCI DSS Gap Assessment Report](https://docs.google.com/document/d/1HV6-M516MptYr3zOR46hnxbGqYXX-RuK/edit?usp=sharing&ouid=101134501969411208830&rtpof=true&sd=true)** , including Google Workspace configuration reviews, admin panel security analysis, service account inventory, and log retention verification.

---

## Key Findings & Recommendations

*   **Inactive User Accounts (High):** Two former staff accounts remained active with no formal offboarding process. *Recommendation*: Implement quarterly access reviews and disable accounts within 24 hours of termination.

*   **Log Tampering Risk (High):** Admin logs stored on the same server as admin users, who could modify logs; no tamper monitoring in place. *Recommendation*: Segregate logs to separate storage with append-only permissions and implement file integrity monitoring.

*   **Missing MFA (Medium):** Admin dashboard accessed via username/password only, with no multi-factor authentication. *Recommendation*: Implement MFA for all administrative access using Google Authenticator plugin.

*   **Insufficient Log Retention (Medium):** Admin panel logs retained for only 30 days, falling short of PCI DSS 90-day minimum. *Recommendation*: Increase retention to 90 days and implement 12-month archiving solution.

*   **Hardcoded Service Account Password (Low):** Database connection used embedded credentials in config files with no rotation schedule. *Recommendation*: Move credentials to environment variables and implement quarterly rotation.

---

## Outcome & Reflection

The assessment confirmed Ikigai's low-risk profile due to its fully outsourced payment model (SAQ A), with no cardholder data touching internal systems. However, foundational security gaps—particularly around access reviews, log protection, and MFA coverage—presented moderate risk to corporate systems supporting e-commerce operations. The findings reinforced that even in reduced-scope environments, basic access and logging controls require formalisation.

---

## Linked Project Documents

[PCI DSS Gap Assessment – E-Commerce Company](https://drive.google.com/drive/folders/1BfAAtvKAkp5tkcBksxKAHdXZVYGDtdQS?usp=sharing)
