# Week 3 Task Security and GDPR

---

## 1. Introduction (≈150 words)

For this task, I evaluated my controller UI navigation system from a networking, security, and compliance perspective. It was originally built in Unreal Engine as a local system for navigating menus with a controller.

The system does not handle or store any personal data, so it does not raise any GDPR concerns in its current form. The current implementation only manages UI navigation, and features that would require storing user data, such as input remapping, are not included in the final build. If these features were added in the future, appropriate data handling and security measures would be required.

---

## 2. Implementation (≈200 words)

The system currently runs locally, but adding networking could allow UI settings or input data to be shared or stored externally. This could introduce risks such as data being accessed or changed, or incorrect data causing issues with the UI. There is also a risk of misuse if the system is set up incorrectly.

To reduce these risks, things like encryption and access control would be needed. Logging could also help track changes. A client–server setup could be used to check data, but this would add complexity and isn’t needed for the core system.

If networking was added, the UI should only handle menus and not change gameplay. Any gameplay changes should be checked on the server.

These risks only apply if the system is extended to use networking or external storage. In its current form, even when built and uploaded to Steam, everything runs locally, so these issues don’t apply.

---

## 3. Outcome (≈150 words)

The system works safely as a local tool and does not introduce any GDPR or security concerns in its current form. It does not store or transmit any data, so the risks identified only apply if networking or external storage is added. While the game itself uses networking for multiplayer, this system does not rely on it and can remain local without introducing additional risk.

The current design also separates UI behaviour from gameplay systems, which reduces the risk of unintended changes and makes the system easier to maintain if it is expanded in the future.

**Demonstration video link:**  

---

## 4. Bibliography

- List all external sources used (documentation, tutorials, articles, etc.)  
- Use the universities referencing style

---

## 5. AI Usage Declaration

- State whether AI tools were used or not  
- If used, name the tool(s) and describe how they were used  

---
















## Submission Notes & Checklist

> Remove this section once complete — use this as a checklist before submitting

- Total word count: **500 words (±10%)** across Sections 1–3  
- **Figure captions and figure descriptions do NOT count towards the word count**  
- Use **plenty of images, GIFs, videos, screenshots, and short code snippets** where appropriate to demonstrate understanding and functionality  
- All required **source code is included in this repository**  
- Any required **executables or builds are provided via GitHub Releases**, where appropriate  
- Demonstration video link is accessible and clearly shows functionality  
- Bibliography includes all referenced material  
- AI usage is clearly declared (or explicitly stated as not used)  
- Work reflects your own understanding and professional practice  

---
