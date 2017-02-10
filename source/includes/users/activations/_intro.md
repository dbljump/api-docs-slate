# Users: activations

Resources related to user account activations.

### How activations work

A new user cannot sign in until they activate their account. Activations work like this:

1. When a user signs up for a new account, they receive an email with a link they must follow to activate their account.
2. The link contains an activation token and the user's email. Clicking the link passes these to the API.
3. On successful activation, the API sets the user attribute `activated_at` to the current time, and returns a JWT the client can use to sign in the activated user.
4. If the user loses their activation email/link, or if it has expired, they can request a new one.
