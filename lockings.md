# Locking Records

- [Introduction](#introduction)
- [Enabling Locking Plugin](#enable)
- [Configuring Records Locking](#configure)
- [Locking Configuration Examples](#examples)
- [Date Range Is Locked Error](#error)

<a name="introduction"></a>
## Introduction

You can use the `Locking` plugin to lock records for modifications on schedule defined for your team. The locking feature applies to users, who do not have the `team:calendar:override_date_lock` or `team:calendar:override_own_date_lock` access right in their role (such as regular users). Supervisors and higher managers, by default, can create and modify records even with the Locking plugin enabled, unless the `team:calendar:override_date_lock` is removed from their role.

Potential applications include a scenario when time entries must be ready by a specific moment for payroll processing, or something similar.

Note 1: The Locking plugin was developed to combat the possible modification of past records.

Note 2: In addition to locking the following situations make records non-editable.
If record is approved with the Report Approval plugin.
We consider such records finalized and prohibit edits. If a record must be edited, remove a condition that locks it.

<a name="enable"></a>
## Enabling Locking Plugin

To enable `locking`, check the Locking box in the `Plugins` section from `Team Settings` and click Save.

<a name="configure"></a>
## Configuring Records Locking

You cann acces it `Team Panel` on sidebar menu you can find `Lockings`. The page that appears allows you to configure how locking works. On it, simply define your cron schedule for locking.

![create-lockings](https://raw.githubusercontent.com/custura/docs/main/preview/lockings.jpg)

<a name="examples"></a>
## Locking Configuration Examples

- Monthly on the 1st at 8:15
```bash
15 8 1 * *
```
When the server time reaches 8:15 on the 1st day of any month, regular users will not be able to enter or modify any records for dates earlier than the first of this month.

- Weekly on Mondays at 10:00
```bash
0 10 * * 1
```
When the server time reaches 10:00 on a Monday, regular users will not be able to enter or modify any records for dates earlier than Monday.
- Biweekly
Unfortunately, cron format does not allow to specify every other week cut-off schedule. Use either monthly or weekly locking instead. If you really need a biweekly schedule, you have to customize Time Tracker, perhaps via a customization job.

<a name="error"> </a>
## Date Range Is Locked Error

When users try to enter or modify records in a locked date interval, they see a Date range is locked error. Locking is not applied to users who have the `team:calendar:override_date_lock` or `team:calendar:override_own_date_lock` right.

![create-lockings](https://raw.githubusercontent.com/custura/docs/main/preview/locking-error.jpg)
