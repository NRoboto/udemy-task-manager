# udemy-task-manager
Weather app created by following "The Complete Node.js Developer Course (3rd Edition)" on Udemy.

This is a RESTful API for a task keeping app. A live version is available [here](https://nroboto-task-manager.herokuapp.com/).

## How to use
Requests which require authentication must have an "Authentication" header containing a bearer token as returned by the "Create" and "Login" routes.
### Users
| Requires Authentication | Action | Method + URL | Request Body | Returns |
|---|---|---|---|---|
|   | Create | POST /users | {name, email, password} | {user, login JWT} |
|   | Login | POST /users/login | {email, password} | {login JWT} |
| ✓ | Logout | POST /users/logout | | |
| ✓ | Logout All Sessions | POST /users/logoutAll | | |
| ✓ | View Profile | GET /users/me | | user |
| ✓ | Update | PATCH /users/me | {name?, email?, password?} | user |
| ✓ | Delete | DELETE /users/me | | |
| ✓ | Upload Avatar | POST /users/me/avatar | {avatar} (form-data) | |
| ✓ | Delete Avatar | DELETE /users/me/avatar | | |
|   | View Avatar | GET /users/:id/avatar | | PNG |

### Tasks
| Requires Authentication | Action | Method + URL | Request Body | Returns |
|---|---|---|---|---|
| ✓ | Create | POST /tasks | {description, completed?} | task |
| ✓ | View All | GET /tasks?completed=<boolean>&limit=<int>&skip=<int>&sortBy=<createdAt\|completed>_<asc\|desc> | | [task] |
| ✓ | View One | GET /tasks/:id | | task |
| ✓ | Update | PATCH /tasks/:id | {description?, completed?} | task |
| ✓ | Delete | DELETE /tasks/:id | | |
