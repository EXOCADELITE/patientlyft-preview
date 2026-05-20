# PatientLyft Clinic Growth Lead Form

This workspace contains the PatientLyft static HTML page with a Supabase-backed service checklist form.

## Files

- `index.patientlyft-with-contact.html` - PatientLyft page with the clinic growth service checklist form wired in.
- `supabase/migrations/20260520123000_create_clinic_growth_leads.sql` - `clinic_growth_leads` table, indexes, and row-level security policy.

## Supabase setup

Run the SQL migration in your Supabase project. It creates `public.clinic_growth_leads`, enables RLS, allows anonymous inserts for new leads with selected services, and does not allow public reads.

Add these environment variables to your frontend project:

```text
VITE_SUPABASE_URL=your-supabase-project-url
VITE_SUPABASE_ANON_KEY=your-supabase-anon-key
```

The form saves:

- `clinic_name`
- `contact_name`
- `email`
- `phone`
- `selected_services`
- `message`
- `status`

It disables the submit button while saving, shows a success message after Supabase accepts the lead, and shows an error message if saving fails.
