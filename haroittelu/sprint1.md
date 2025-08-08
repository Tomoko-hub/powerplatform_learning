Project Notes – Week Summary
Date: 04–08 August 2025


1. Main Topics Covered This Week
1.1 Dataverse Capacity Discussion
While creating a new environment, we encountered the error:
"This environment can't be created because your org (tenant) needs at least 1 GB of database capacity."

This indicates that the company’s Dataverse capacity is already near its limit.

We identified three possible solutions:

Delete unused data to free capacity.

Purchase additional capacity (recommended if production usage is planned).

Use Pay-as-you-go with Azure (not preferred for this case).

Decision: Proceed with the current production environment and monitor capacity.
Additional capacity purchase will be proposed only if usage reaches critical levels.

1.2 Current Impact Assessment
No existing custom apps in the company; only email and document services are in use.

Risk to other services is minimal, but Dataverse capacity is a shared resource, also used by Dynamics 365 (if licensed).

The Työtuntiseuranta app will mainly store text, numbers, and dates; no large file attachments planned until late stages (PDF reports).

Capacity consumption will be minimal in the short term.

1.3 Naming Conventions for Dataverse
We established a consistent naming scheme to prevent conflicts and ensure clarity:

Tables:

Prefix with app code TT_ (Työtuntiseuranta).

Example: TT_Tyontekija, TT_Tyotunti.

Fields:

Prefix with table abbreviation.

Example in TT_Tyotunti:

Tt_Pvm (Date)

Tt_Tunnit (Hours)

Tt_PoissaoloSyy (Absence Reason)

Benefits:

Easy filtering in Dataverse and Power Automate.

Prevents confusion when multiple apps exist in the same environment.

1.4 Sandbox vs. Production
A Sandbox environment is not required for this project because:

No other apps exist in the environment.

Short 7-week timeline.

Additional environment creation is blocked due to capacity.

Development will be done directly in Production using:

Mock data for testing.

Developer-only screens for safe changes.

If future changes require isolated testing, a Sandbox can be considered after capacity is increased.

1.5 Capacity Monitoring Plan
Mid-project (Sprint 5) we will check Dataverse capacity usage via Power Platform Admin Center.

If capacity usage is high:

Consider removing test data.

Propose capacity add-on purchase.

PDF report generation is planned for the final stage; by then, any critical capacity issues should already be visible.

2. Key Decisions
Proceed in Production Environment with proper naming conventions and mock data during early sprints.

No immediate capacity purchase; monitor usage and propose purchase only if critical.

Use Developer Mode UI for testing features without affecting live data.

3. Next Steps (Sprint 2)
Build Dataverse tables (TT_Tyontekija, TT_Tyotunti, etc.).

Input mock data for development and testing.

Begin implementing login and time-entry logic in Power Apps.

This README section records the reasoning behind our environment choice, capacity management strategy, and table/field naming conventions for future reference.

