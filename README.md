# Just-In-Time Privileged Access (PIM) - Microsoft Entra ID

## Problem Statement

Standing admin access creates unnecessary risk. If an admin account is
compromised, an attacker gains permanent, unrestricted privileged access
with no extra verification required. Many organizations assign roles like
Global Administrator or Groups Administrator as permanent, "always-on"
assignments, even though most admin tasks are infrequent. This leaves a
large attack surface open at all times.

## Solution Overview

I implemented Microsoft Entra Privileged Identity Management (PIM) to
enforce a just-in-time access model instead of standing privilege. Rather
than holding the Groups Administrator role permanently, I configured it as
an **eligible** assignment that requires explicit activation, multifactor
authentication, and a written justification before granting temporary
access. I also demonstrated the contrast between this model and a
traditional permanent assignment (Global Administrator) within the same
tenant.

## Tools Used

- Microsoft Entra ID (P2 license)
- Privileged Identity Management (PIM)
- Azure Portal
- Microsoft Entra Conditional Access / MFA

## Project Timeline

- Step 1: Assigned Groups Administrator as an **eligible** (not active) role
- Step 2: Configured activation policy: required Azure MFA and justification
on activation
- Step 3: Diagnosed and resolved a "policy is invalid" error caused by
selecting an unconfigured Conditional Access authentication context, and
corrected it by switching to standard Azure MFA
- Step 4: Activated the role through the actual end-user workflow, providing
a justification and duration
- Step 5: Verified the activation in "Active assignments," confirming a
time-boxed (temporary) session distinct from a standing/permanent role

## Key Accomplishments

- Replaced standing privileged access with a just-in-time, eligible-based
model for a directory role
- Enforced MFA and justification requirements on role activation
- Diagnosed and fixed a real configuration error (invalid authentication
context) rather than just following a checklist
- Demonstrated the practical difference between a **temporary, activated** assignment and a **permanent, standing** assignment within the same tenant
