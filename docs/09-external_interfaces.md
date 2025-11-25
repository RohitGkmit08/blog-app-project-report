# 10. External Interfaces

This section describes the external systems and interfaces that interact with the Blogging Application.

---

| Interface | Description |
|------------|-------------|
| **SMTP Email Server** | Provides email delivery functionality. The backend uses NodeMailer (an internal library) to connect and send automated blog update emails via an external SMTP service such as Gmail, Outlook, or a custom domain mail server. |
| **Web Browser** | Acts as the primary user interface, allowing users to read blogs, post comments, and manage subscriptions. |
| **Hosting Environment** | Provides cloud-based hosting for the backend (AWS EC2) and frontend (Vercel), ensuring continuous uptime and public accessibility. |

---

## Summary

- **NodeMailer** is an internal tool integrated into the Express backend.  
- **SMTP Server** (e.g., Gmail, Outlook, or custom mail host) is the actual **external interface** responsible for sending emails.  
- The frontend and backend communicate through standard **HTTP/HTTPS interfaces** hosted in a cloud environment.

---

