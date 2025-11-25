| TC ID | Module | Scenario | Inputs | Expected Output |
|-------|--------|------------------------|--------|-----------------|
| **Authentication Module** | | | | |
| TEST_CASE_01 | Auth Service | Create user with valid data | {name, email, password} | Returns user object without password |
| TEST_CASE_02 | Auth Service | Duplicate email registration | Existing email | Throws "Email already exists" |
| TEST_CASE_03 | Auth Service | Login with valid credentials | {email, password} | Returns user + token |
| TEST_CASE_04 | Auth Service | Invalid password | {email, wrongPassword} | Throws "Invalid credentials" |
| TEST_CASE_05 | Auth Service | Valid payload | {userId, role} | Returns JWT string |
| TEST_CASE_06 | Auth Utils | Compare hashed and plain | (plain, hash) | Returns true |
| **Blog Module** | | | | |
| TEST_CASE_07 | Blog Service | Create blog with valid data | Title, content, userId | Returns saved blog |
| TEST_CASE_08 | Blog Service | Missing title | No title | Throws validation error |
| TEST_CASE_09 | Blog Service | Valid blog ID | Blog ID | Returns blog object |
| TEST_CASE_10 | Blog Service | Blog not found | Invalid ID | Returns null / error |
| TEST_CASE_11 | Blog Service | Valid update | ID + updates | Returns updated blog |
| TEST_CASE_12 | Blog Service | Unauthorized user | Other user | Throws unauthorized error |
| TEST_CASE_13 | Blog Service | Valid delete | Blog ID | Returns deletion success |
| TEST_CASE_14 | Blog Service | Non-existent blog | Invalid ID | Throws not-found error |
| **Comment Module** | | | | |
| TEST_CASE_15 | Comment Service | Add valid comment | {blogId, userId, text} | Returns created comment |
| TEST_CASE_16 | Comment Service | Approve comment | {commentId, action: approve} | Comment updated |
| TEST_CASE_17 | Comment Service | Reject comment | {commentId, action: reject} | Comment updated |
| TEST_CASE_18 | Comment Service | Valid deletion | commentId | Returns delete success |
| **User Module** | | | | |
| TEST_CASE_19 | User Service | Fetch profile | userId | Returns user profile |
| TEST_CASE_20 | User Service | Valid update | {userId, updates} | Returns updated profile |
| TEST_CASE_21 | User Validation | Valid data | Correct input | Passes validation |
| TEST_CASE_22 | User Validation | Missing required fields | Missing email | Returns validation error |