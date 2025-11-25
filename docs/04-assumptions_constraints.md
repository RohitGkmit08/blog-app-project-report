# 4. Assumptions, Constraints, and Dependencies

This section outlines the underlying assumptions, project limitations, and third-party dependencies that impact the overall functioning of the Blogging Application.

---

## Assumptions

- Users have access to a stable internet connection.  
- Subscribed users provide valid and active email addresses.  
- Admins are verified and registered users within the system.  
- SMTP credentials for NodeMailer are correctly configured and active.  
- Frontend and backend environments have consistent configurations (e.g., API base URLs, authentication tokens).

---

## Constraints

- Only **approved comments** are displayed publicly under each blog post.  
- Email frequency is limited to **new blog post notifications** — no manual or promotional campaigns.  
- Email delivery reliability depends on **SMTP server uptime** and **NodeMailer configuration**.  
- The system must comply with spam regulations (e.g., users can unsubscribe).  
- Rate limiting and retry mechanisms must respect SMTP provider policies.  
- Frontend and backend deployments are bound by respective hosting service limits (Vercel and AWS EC2).

---

## Dependencies

- **MongoDB (Database Storage):**  
  Stores blog data, user profiles, comments, and subscription preferences.

- **NodeMailer (Email Delivery):**  
  Handles automated notification emails (e.g., new blog alerts) using an SMTP transport such as Gmail, Outlook, or custom domain SMTP servers.

- **Cloud Hosting Environment:**  
  Ensures uptime and accessibility of the frontend (Vercel) and backend (AWS EC2) components.

---

## Summary

The assumptions, constraints, and dependencies collectively ensure:
- Consistent email communication via NodeMailer and SMTP.  
- Secure and verified user interactions.  
- Dependable system behavior across hosted environments.  

These considerations help maintain system reliability, compliance, and scalability.

---

