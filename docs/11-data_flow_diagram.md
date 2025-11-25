
# Data Flow Diagram

This document presents the three levels of Data Flow Diagrams (DFD) for the **Blog Management Application**, showing how data moves between users, the frontend, backend, and supporting services.

---

## Level-0 DFD — Context Diagram

**Explanation:**
The Level-0 DFD (Context Diagram) shows the entire Blog Management System as a single process and how it exchanges data with external entities (User and Admin). It also shows the single logical Database used by the system.

```mermaid
graph TD

%% ===============================
%% Level 0 DFD - Blogging Application
%% ===============================

%% External Entities
U[User]
A[Admin]

%% Process
P1[(Blog Management System)]

%% Data Store
D1[(Database)]

%% Data Flow
U -->|Registers / Logs in / Views Blogs| P1
A -->|Manages Blogs / Categories / Users| P1
P1 -->|Stores / Retrieves Data| D1
D1 -->|Provides Stored Data| P1
P1 -->|Displays Blogs / Messages / Results| U
P1 -->|Dashboard / Reports| A

```

## Level-1 DFD - System Decomposition

This document presents the three levels of Data Flow Diagrams (DFD) for the **Blog Management Application**, showing how data moves between users, the frontend, backend, and supporting services.

**Explanation:**
The Level-1 DFD decomposes the Blog Management System into major subsystems (User Authentication, Blog Management, Category Management, Comment System) and shows their interactions with the data stores (Users, Blogs, Categories, Comments) and with external actors (User and Admin).

```mermaid
graph LR

U["User"]
A["Admin"]

subgraph Blog_Management_System["Blog Management System"]
  direction TB
  P1A["User Authentication"]
  P1B["Blog Management"]
  P1C["Category Management"]
  P1D["Comment System"]
end

subgraph Data_Stores["Data Storage"]
  direction TB
  D1["Users Database"]
  D2["Blogs Database"]
  D3["Categories Database"]
  D4["Comments Database"]
end

U -->|"Register or Login"| P1A
P1A -->|"Verify Credentials and Hash Password"| D1
D1 -->|"User Info"| P1A
P1A -->|"Access Token or Auth Status"| U

U -->|"Create, View, or Edit Blogs"| P1B
P1B -->|"Store or Retrieve Blogs"| D2
D2 -->|"Blog Data"| P1B
P1B -->|"Display Blogs"| U

P1A -->|"Authenticated Access"| P1B

A -->|"Add, Edit, or Delete Categories"| P1C
P1C -->|"Update Categories"| D3
D3 -->|"Category Data"| P1C
P1C -->|"Provide Category List"| P1B
P1B -->|"Selected Category Reference"| P1C

U -->|"Post or View Comments"| P1D
P1D -->|"Read or Write Comments"| D4
D4 -->|"Comments Data"| P1D
P1D -->|"Display Comments"| U

P1B -->|"Provide Blog Context"| P1D
P1D -->|"Comments for Blog"| P1B

A -->|"Manage Users and Blogs"| P1A
A -->|"Moderate Content"| P1B
A -->|"Monitor Comments"| P1D
```
## Authentication and Authorization 

**Explanation**

This document presents the authentication and authorization flow for the **JWT-based Application**, showing how user registration, login, token verification, and permission checks are handled between users, the frontend, backend, and supporting services.

```mermaid
flowchart TD
    subgraph A [User Registration]
        A1[User submits registration data<br/>name, email, password] --> A2[Hash password for security]
        A2 --> A3[Save record in UsersDB]
        A3 --> A4[Return success message]
    end

    subgraph B [User Login]
        B1[User enters credentials] --> B2{Validate credentials<br/>against UsersDB}
        B2 -- Valid --> B3[Create & Sign JWT<br/>using Secret Key]
        B3 --> B4[Return token to user]
        B2 -- Invalid --> B5[Return error message]
    end

    subgraph C [Token Verification]
        C1[API Request with JWT<br/>in header] --> C2{Verify token signature<br/>using JWT Secret}
        C2 -- Valid --> C3[Decode token to extract<br/>user details & role]
        C2 -- Invalid --> C4[Return authentication error]
    end

    subgraph D [Authorization Process]
        C3 --> D1[Check user role against<br/>Access Control List]
        D1 --> D2{Authorize: Compare requested<br/>action with ACL rules}
        D2 -- Permissions Match --> D3[Access Granted]
        D2 -- Insufficient Rights --> D4[Access Denied]
    end

    A --> B
    B --> C
    C --> D

```
