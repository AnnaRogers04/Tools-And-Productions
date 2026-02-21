# Task Title

---

## 1. Introduction (≈150 words)

The selected tool is a UI State Management System built as a reusable Unreal Engine plugin. It currently runs locally and controls menu states such as Pause, Options, and Controls. However, if used in a multiplayer or online environment, it must be evaluated for networking, security, and data compliance risks.

Although it does not currently send data over a network, future versions could include saved preferences or online integration. This introduces risks such as data exposure or client-side manipulation. Evaluating these risks ensures the tool remains secure and suitable for professional use. 

---

## 2. Implementation (≈200 words)

The tool currently runs only on the client and does not send any data over a network. However, if it is expanded to support online features like cloud-saved settings, it would need secure communication. In that case, HTTPS over TCP with TLS encryption should be used to protect data in transit.

Risks could include exposure of player preferences or manipulation of UI settings. To reduce this risk, the UI should remain presentation-only and not directly change gameplay values. Any gameplay changes should be validated on the server in a client–server model.

Authentication should use secure tokens, and access to administrative features should be restricted. Logging should track configuration changes. To meet GDPR principles, only essential data should be stored, and users must be able to access or delete their information.

---

## 3. Outcome (≈150 words)

The current tool is low risk because it runs locally and does not send data over a network. However, if networking is added in the future, risks such as data exposure or client manipulation could appear. Using a client–server model with server-side validation would reduce these risks and improve trust.

Networking could be useful for features like centralised setting validation or shared configuration tools. However, adding networking without a clear purpose would increase complexity and potential security risks. If the system remains purely UI-based and cosmetic, keeping it local is safer and simpler. The current architecture supports future expansion because it separates UI presentation from gameplay logic.
- Provide a link to a short demonstration video  


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
