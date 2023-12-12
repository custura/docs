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
All default `Manager` role rights. They are described below
 - team:locking:*
    #uses for:
        #-
```
#### Manager
Manager supervises a group of users, clients, supervisors, and co-managers by having most of access to team data. A person with mostly full set of permissions to a group.
```bash
Access rights:
Has all of the `Co-manager` role permissions plus the following.
 - team:holiday:team:crud
    #uses for:
        #-
 - team:monthlyquotas:*
    #uses for:
        #-
 - team:role:create
    #uses for:
        #-
 - team:role:delete
    #uses for:
        #-
 - team:role:read
    #uses for:
        #-
 - team:role:update
    #uses for:
        #-
 - team:setting:manage_configs
    #uses for:
        #-
 - team:setting:manage_plugins
    #uses for:
        #-
 - team:setting:update
    #uses for:
        #-
```
#### Co-manager
Co-manager performs some of team management tasks such as working with users, projects, tasks, generating reports. This role is useful for big teams. Small teams may do without co-managers. This role is almost like a team manager, but some tasks still require a manager to login. In other words, a co-manager is a person with an extended set of team management functions, who is helping a team manager with most of the work.
```bash
Access rights:
Has all of the `Supervisor` role permissions plus the following.
 - team:appointment:delete
    #uses for:
        #-
 - team:calendar:override_date_lock
    #uses for:
        #-
 - team:client:create
    #uses for:
        #-
 - team:client:delete
    #uses for:
        #-
 - team:client:update
    #uses for:
        #-
 - team:holiday:create
    #uses for:
        #-
 - team:holiday:delete
    #uses for:
        #-
 - team:medical:delete
    #uses for:
        #-
 - team:project:create
    #uses for:
        #-
 - team:project:delete
    #uses for:
        #-
 - team:project:update
    #uses for:
        #-
 - team:report:create
    #uses for:
        #-
 - team:task:create
    #uses for:
        #-
 - team:task:delete
    #uses for:
        #-
 - team:task:read
    #uses for:
        #-
 - team:task:update
    #uses for:
        #-
 - team:template:create
    #uses for:
        #-
 - team:template:delete
    #uses for:
        #-
 - team:template:read
    #uses for:
        #-
 - team:template:update
    #uses for:
        #-
 - team:user:create
    #uses for:
        #-
 - team:user:delete
    #uses for:
        #-
 - team:user:update
    #uses for:
        #-
 - team:vacation:delete
    #uses for:
        #-
```
#### Supervisor
Supervisors have a small set of management functions in a team. 
```bash
Access rights:
They have all of default `Member` role permissions plus the following.
 - team:appointment:approve
    #uses for:
        #-
 - team:appointment:read
    #uses for:
        #-
 - team:chart:view
    #uses for:
        #-
 - team:client:read
    #uses for:
        #-
 - team:holiday:read
    #uses for:
        #-
 - team:medical:approve
    #uses for:
        #-
 - team:project:read
    #uses for:
        #-
 - team:role:read
    #uses for:
        #-
 - team:task:read
    #uses for:
        #-
 - team:template:read
    #uses for:
        #-
 - team:user:read
    #uses for:
        #-
 - team:users:view
    #uses for:
        #-
 - team:vacation:update
    #uses for:
        #-
```
#### Member
Users work with App by entering data and generating reports for themselves. By default, they do not have any management rights. Primary function for users is data entry and viewing their own data.
```bash
Default Member role access rights:
 - team:calendar:track 
    #uses for: 
        #- calendar track
        #- unschedule appointment in calendar
        #- update appointment in calendar
        #- delete appointment in calendar
        #- change appointment date in calendar
 - team:appointment:view_own
    #uses for:
        #- view own appointments in team panel
 - team:chart:view_own
    #uses for:
        #- view own charts in team panel
 - team:client:view_own
    #uses for:
        #- view own clients in team panel
 - team:project:view_own
    #uses for:
        #- view own projects in team panel
 - team:report:view_own
    #uses for:
        #- generate reports with own records in team panel
 - team:task:view_own
    #uses for:
        #- view own tasks in team panel
 - team:template:view_own
    #uses for:
        #- view own templates in team panel
 - team:user:view_own
    #uses for:
        #- view own informations in team panel members
 - team:calendar:override_own_date_lock
    #uses for:
        #- override own date for appointment in calendar
 - team:medical:create
    #uses for:
        #- create medicals in team panel
 - team:vacation:create
    #uses for:
        #- create vacations in team panel
```
#### Client
Client role is used with the Clients plugin. When it is enabled, a client user (which is external to a team) is a normal user to our platform and can view own data such as reports, charts in your team. 
Clients do not have the calendarTrack right but can view what is entered into App by other users and is associated with this client.
```bash
Default client role access rights:
 - team_client:view_own
    #uses for:
        #-
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
team_client:view_own    - is for client user, allows him/she to see what belongs to him/she.
team:client:view_own    - can read own clients.
team:client:create      - allows user to create new clients.
team:client:update      - allows user to update existing clients.
team:client:read        - allows user to read clients belonging to the team.
team:client:delete      - can delete existing clients.
```

#### Holidays
```bash
team:holiday:view_own   - can read holidays belongs to.
team:holiday:team:crud  - allows user to manage team existing holidays.
team:holiday:create     - allows user to create holidays for team.
team:holiday:read       - can read holidays.
team:holiday:delete     - allows user to delete holidays for members.
```

#### Medicals
```bash
team:medical:view_own   - can read medicals belongs to.
team:medical:create     - allows user to create medicals.
team:medical:read       - can read medicals belonging to the team..
team:medical:approve    - allows user to approve/disapprove other team members medicals in team panel.
team:medical:delete     - allows user to delete medicals for members.
```

#### Projects
```bash
team:project:view_own   - can read projects belongs to.
team:project:create     - allows user to create team projects.
team:project:read       - can read team projects.
team:project:update     - allows user to update existing projects.
team:project:delete     - allows user to delete team projects.
```

#### Reports
```bash
team:report:view_own - can generate reports with his own records.
team:report:create   - can generate reports for all members of team.
```

#### Charts
```bash
team:chart:view_own - can view charts belongs to.
team:chart:view     - can view charts for all members of team
```

#### Team Roles
```bash
team:role:create - allows user to create team roles.
team:role:read   - can read team roles.
team:role:update - allows user to update existing team roles.
team:role:delete - allows user to delete existing team roles.
```

#### Tasks
```bash
team:task:view_own  - can read tasks belongs to.
team:task:create    - allows user to create tasks.
team:task:read      - can read tasks.
team:task:update    - allows user update existing tasks.
team:task:delete    - allows user to delete existing tasks.
```

#### Templates
```bash
team:template:view_own  - can read templates belong to.
team:template:create    - allows user to create templates.
team:template:read      - can read templates.
team:template:update    - allows user to update existing templates.
team:template:delete    - allows user to delete existing templates.
```

#### Vacations
```bash
team:vacation:view_own  - can read vacations belongs to.
team:vacation:create    - allows user to create vacations.
team:vacation:read      - can read vacations belonging to the team.
team:vacation:approve   - allows user to approve/disapprove other team members vacations in team panel.
team:vacation:delete    - allows user to delete vacations for members.
```

#### Monthly Quotas
```bash
team:monthlyquotas:* - allows user to manage monthly quotas.
```

#### Lockings
```bash
team:locking:* - allows user to manage lockings.
```
