# Security principles

1. **Never expose data across organisations.**
2. **Server is the authority.** UI hiding is not security.
3. **Least privilege.** Organisation Owner is not a medical reader by default.
4. **Sensitive modules are opt-in and extra-permissioned.**
5. **Audit who, what, when, event, record, before, after.**
6. **Do not silently modify operational history.**
7. **Minimise.** If a control operator does not need a surname to dispatch, do not put it on the wall.
8. **Assume a laptop will be stolen in a production office.** MFA, short sessions for privileged roles, remote revoke.
9. **Assume a developer will make a mistake.** RLS is the backstop.
10. **Humans decide emergencies.** Software does not.

This is a serious SaaS product used around real harm. Treat it that way from the first table.
