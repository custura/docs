# Monthly Quotas

- [Introduction](#introduction)

<a name="introduction"></a>
## Introduction

Plugin adds a capability for users to see their monthly work hour quotas and apprear a new menu within name `Monthly Quotas` in Team Panel.

Quota (%) is a user setting. It can be configured on member edit pop-up (Team Panel - Members, User edit or Add). It is used with Monthly Quotas plugin, which displays time quotas information to users when they work with their time (on calendar).

With enabled Monthly Quotas plugin, one can define time quotas for each month, by either specifying the number of hours and minutes directly, or by multiplying work days and workday hours. This quota is treated as 100% quota, available to a full-time employee.

Organizations may have different types of users such as full-time, part-time, contractors, etc. In such situation, one can additionally define a Quota Percent to each user, which may be different from 100%. For example:

Full-time worker - quota 100%.
Part-time worker - quota 50%.
Contractor - quota 33.33%.

When set, this Quota Percent option changes the quota calculation algorithm for user accordingly. Empty, or non-set value means 100% of available quota.
