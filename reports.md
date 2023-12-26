# Reports

- [Introduction](#introduction)
- [Selecting Time Period](#time-period)
- [Selecting Members](#members)
- [Filtering by Client](#filtering-by-client)
- [Filtering by Project or Task](#filtering-by-project-or-task)
- [Approved vs Not Approved Items](#approved-notapproved)
- [Selecting Fields to Display](#fields)
- [Grouping Report Items](#grouping)

<a name="introduction"></a>
## Introduction

You can do reporting in Application using the Reports page.<br>
Reporting works differently depending on member role.<br>
Regular Members can create and view reports for themselves.<br>
Supervisors can additionally do reporting for lower rank roles.<br>
Clients can do reporting for a single client.<br>
Top manager, Managers and Co-managers can do reporting for the entire team.<br>
The above applies to unmodified member roles. For customized roles the ability to do reporting depends on having team:report:view_own, team:report:create, or team_client:view_own in member role.<br>

Fields and options available in reports depend on which features are enabled for your group. For example, when Clients plugin is enabled, you can filter or group reports by client. To configure and to turn on extra features use the Plugins tab.

<a name="time-period"></a>
## Selecting Time Period

Use controls in the Select time period block to select a time interval for reporting. For example, you can select intervals like this month, previous month, or select a range between specific dates.

<a name="members"></a>
## Selecting Members

The Select members section on the Reports page allows you to select members for reporting. Use checkboxes to select / deselect individual members.

<a name="filtering-by-client"></a>
## Filtering by Client

Client dropdown control is available when clients are enabled. Use it to filter report items for a single client.

<a name="filtering-by-project-or-task"></a>
## Filtering by Project or Task

Use the Project and Task controls to filter report by project or task.
- Projects dropdown is available in both projects and projects and tasks tracking modes.
- Task dropdown is available in projects and tasks tracking mode.

<a name="approved-notapproved"></a>
## Approved vs Not Approved Items

The Approved selector is available on reports when you use the Report approval plugin. It allows to select approved, not approved, or all records for reporting.

![Report Approved](https://raw.githubusercontent.com/custura/docs/main/preview/reports-approved.jpg)

<a name="fields"></a>
## Selecting Fields to Display

Use the Show fields block to select columns for report.

![Report Fields](https://raw.githubusercontent.com/custura/docs/main/preview/reports-fields.jpg)

<a name="grouping"></a>
## Grouping Report Items

Team reports can be optionally grouped using the following entities:
- date
- user
- client
- project
- task
