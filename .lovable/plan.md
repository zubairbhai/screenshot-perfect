# AVN Student Results Portal

## Experience
- Replace the blank home page with the AVN-branded student sign-in and results experience, using the supplied banner and reference layout.
- Let rostered students sign in with their hall ticket as both username and password. Preserve source rows, clearly label synthetic demo records, and show the selected synthetic record for the shared demo ticket as requested.
- Add an administrator sign-in and a private `/admin` page listing student result lookups with date and time. Keep the supplied administrator credentials in encrypted project secrets; mark this access method as demonstration-only.
- Show student identity, branch, R25 term information, branch-specific subjects, source grades/results, marks, subject totals, pass/fail counts, and an indicative marks-based GPA. Label GPA as indicative because the uploaded source has no credits or official GPA.

## Data and security
- Enable Lovable Cloud email/password auth for app-managed hall-ticket accounts; provision credentials only after checking a ticket against the roster.
- Add Students, Subjects, Results, Student Profiles, user roles, and lookup-history records with explicit grants and strict row-level policies. Student reads remain scoped to the linked student; only the admin role can read all lookup history.
- Import all 873 uploaded rows and their subject/result data without rewriting source values. Add five conspicuously synthetic records so the demo set has exactly 2 PASS and 3 FAIL records.
- Preserve both records for the shared ticket: keep its uploaded academic row intact while routing sign-in to the synthetic demo row.

## Technical details
- Use TanStack Start server functions for roster validation, account provisioning, student-owned results, and admin-only lookup history. Keep privileged clients inside authorized server handlers.
- Normalize hall-ticket comparisons without altering original roster values. Use subject codes only where directly supported by the supplied reference; otherwise show that codes were not supplied.
- Add tests for the 40/60 demo distribution and mark-based GPA behavior; run existing routing tests and verify student/admin flows in the preview where possible.
