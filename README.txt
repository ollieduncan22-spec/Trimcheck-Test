TrimCheck Password Recovery TEST Upgrade

Upload index.html and owner.html to the Trimcheck-Test GitHub repo root (replace existing files). Do not replace the working App repo or Android APK.

SUPABASE CONFIGURATION REQUIRED:
Authentication > URL Configuration > Redirect URLs: add exactly:
https://ollieduncan22-spec.github.io/Trimcheck-Test/index.html?mode=recovery

Supabase's reset-password email template must link using {{ .ConfirmationURL }} (default).
If the email template uses {{ .TokenHash }} instead, configure a matching token_hash recovery URL or restore the default template.

TEST:
1. Open test homepage in a private/incognito tab. Click Forgot password, enter test email.
2. Open latest reset email; should show new-password form. Choose password >=12 characters, confirm, submit.
3. Sign in using new password. Test change-password button.
4. Check owner sign-in redirect, owner sign-out, and salesperson login.

NOT YET PRODUCTION READY:
- Password change while signed in uses native prompt dialogs for this test. Replace with polished form and reauthentication as appropriate before launch.
- Supabase Auth email delivery/rate limits and custom SMTP must be configured for commercial use.
- Manager dashboards, RLS/tenant isolation, staff invitation roles, and APK integration still require audit.
- Recovery links must not be shared. Do not enter real customer data.
