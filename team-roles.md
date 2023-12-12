# Encryption

- [Introduction](#introduction)
- [Default Roles](#default-roles)
- [Custom Roles](#custom-roles)
- [Role Permissions](#role-permissions)

<a name="introduction"></a>
## Introduction

Each group has a customizable collection of roles and some predefined roles, to one of each every user is assigned. In addition, there is a broader Owner role to manage an entire Team. Role editor is available from a link in Team Panel.
Each role is assigned with a set of access rights(permissions), each allowing access to something, which is explained here.

Below are descriptions of predefined roles.

<a name="default-roles"></a>
## Defaul Roles

#### Owner
Owner user usually creates the team and initially configures the team.
Owner role is not editable.
```bash
Access rights:
['*'] - can administer the team as a whole.
```
#### Top manager
Top manager is a top role in a team. A team in this case is the entire organization. This non-editable role has a full collection of possible access rights, with an exception of "['*']", which is reserved for team Owner (see the Owner role above). In other words, top manager role is an intrinsic, non-editable role for a general manager in an organization (root manager, owner) with all possible rights in a group all the way down. It is assigned to a trusted person. Accounts in one organization (main team) do not relate to accounts in other organizations (other teams) in any way. This means that a user can have several teams.
```bash
Access rights:
All default Manager role rights. Plus other.
 - 
 - 
```
#### Manager
Manager supervises a group of users, clients, supervisors, and co-managers by having most of access to team data. A person with mostly full set of permissions to a group.
```bash
Access rights:
All of the Co-manager role permissions plus other.
 - 
 -
```
#### Co-manager
Co-manager performs some of team management tasks such as working with users, projects, tasks, generating reports. This role is useful for big teams. Small teams may do without co-managers. This role is almost like a team manager, but some tasks still require a manager to login. In other words, a co-manager is a person with an extended set of team management functions, who is helping a team manager with most of the work.
```bash
Access rights:
Has all of the Supervisor role permissions plus other.
 -
 -
```
#### Supervisor
Supervisors have a small set of management functions in a team. 
```bash
Access rights:
They have all of default User role permissions plus other.
 -
 -
```
#### Member
Users work with App by entering data and generating reports for themselves. By default, they do not have any management rights. Primary function for users is data entry and viewing their own data.
```bash
Default Member role access rights:
 -
 -
```
#### Client
Client role is used with the Clients plugin. When it is enabled, a client user (which is external to a team) is a normal user to our platform and can view own data such as reports, charts in your team. 
Clients do not have the calendarTrack right but can view what is entered into App by other users and is associated with this client.
```bash
Default client role access rights:
 -
 -
```
<a name="custom-roles"></a>
## Custom Roles

A user with team:role:create or team:role:update permission has a capability to create and modify additional custom roles in team. New roles can be assigned a subset of access rights(permissions) that such user has. This is accomplished with Role editor as explained below. The same editor can be used to customize or delete roles that belongs to your team.

<a name="role-permissions"></a>
## Role Permissions

Below you can see all available permissions

#### Calendar
```bash
team:calendar:track                     - member can use calendar to track appointments.
team:calendar:override_date_lock        - allows override date lock for lower rank roles.
team:calendar:override_own_date_lock    - allows override date lock for self.
```

#### User
```bash
team:user:view_own  - can view all what belongs to current user model logged.
team:users:view     - can view users belongs to team.
team:user:read      - can read users data in team panel.
team:user:create    - can add/invite a new user to team.
team:user:delete    - can remove user from team.
team:user:update    - can update a team member.
```

#### Settings
```bash
team:setting:update         - allows to update team settings.
team:setting:manage_configs - allows to manage team configs.
team:setting:manage_plugins - allows to manage team plugins.
```

#### Appointments
```bash
team:appointment:view_own   - can read own appointments.
team:appointment:read       - can read other team members appointments in team panel.
team:appointment:approve    - can approve/disapprove other team members appointments in team panel.
team:appointment:delete     - can delete appointments.
```

#### Clients
```bash
team:client:view_own - can read own clients.
team:client:create  - allows user to create new clients.
team:client:update  - allows user to update existing clients.
team:client:read    - allows user to read clients belonging to the team.
team:client:delete  - can delete existing clients.
```
