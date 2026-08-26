# Users

## User resources

`/users` uses type `user`.

Method | Path | Authorization
------ | ---- | -------------
GET | `/users` | Public
GET | `/users/{id}` | Public
POST | `/users` | Public registration
PATCH | `/users/{id}` | Same user or admin
DELETE | `/users/{id}` | Same user, or admin deleting a non-admin
PATCH | `/user-onboarding/{id}` | Same user or admin
PATCH | `/user-preferences/{id}` | Same user or admin

### Registration

Writable registration fields are `email`, `username`, `password`,
`passwordConfirmation`, `acceptedTerms`, and `editorRequest`.

Email must be valid and unique. Username must be unique, contain only letters,
numbers, underscores, or dots, begin and end with a letter or number, and be
2–12 characters. Password must be 8–24 characters. Terms acceptance is
required.

Registration returns `201 Created` and sends an activation email.

### Updating a user

A user or admin can write `unconfirmedEmail`, `username`, `acceptedTerms`,
`base64Image`, `removeAvatar`, `givenNames`, `familyName`, `gender`,
`birthday`, `place`, `password`, and `passwordConfirmation`.

Only admins can also write `role` and `editorRequestApproved`. Roles are
`member`, `editor`, and `admin`.

Approving an editor request enrols the user in contributor onboarding and
queues the welcome email that begins the journey. Repeating an approval does
not replace existing progress or send the welcome email again. A user whose
`onboardingEmails` preference is `false` is still enrolled but does not receive
the onboarding email.

Email and administrative metadata are returned only to the same user or an
admin. Public responses include `username`, `role`, names, `gender`,
`birthday`, `avatar`, `avatarThumb`, and `place`.

For the same user or an admin, the response `meta` also contains the private
`onboarding` and `preferences` objects described below. `onboarding` is `null`
until the user has been enrolled. Preferences are returned with defaults
applied even when the user has not saved an explicit choice.

> Private user state in a `GET /users/{id}` response

```JSON
{
  "meta": {
    "onboarding": {
      "visitEditorComplete": true,
      "chooseArticleComplete": false,
      "uploadImageComplete": false,
      "addCitedTextComplete": false,
      "viewContributionsComplete": false,
      "journeyComplete": false
    },
    "preferences": {
      "notifications": {
        "onboardingEmails": true
      },
      "editor": {
        "showOnboardingReminders": true
      }
    }
  }
}
```

Queryable fields are `id`, `username`, `gender`, `role`, `placeId`,
`editorRequestOpen`, `lastSignedInAt`, `activatedAt`, `birthday`,
`lastActiveAt`, `createdAt`, and `updatedAt`.

## Contributor onboarding

`PATCH /user-onboarding/{id}` records one or more completed tasks in an active
contributor onboarding journey. Replace `{id}` with the user ID and use the
same value for `data.id`. The resource type is `userOnboarding`.

The endpoint accepts partial updates. Every supplied value must be the JSON
boolean `true`: completion is permanent and cannot be reset through this
endpoint. Repeating a completed task is safe and returns the unchanged current
state. The response always includes all task flags and `journeyComplete`, which
becomes `true` after every task is complete.

The same user or an admin can update the resource. The target user must already
be enrolled in contributor onboarding. The endpoint has no `GET`, `POST`, or
`DELETE` action; clients obtain the current state from `GET /users/{id}`.

On approval, the API sends the welcome email and schedules a first-step
reminder for one week later. The first successful `visitEditorComplete` update
schedules a contribution reminder for one week later. Completing the journey
queues its completion email immediately. Before delivery, delayed messages
recheck the user's contributor role, email preference, and relevant progress;
messages that are no longer applicable are cancelled.

> Complete one onboarding task

```JSON
# PATCH /user-onboarding/5
{
  "data": {
    "type": "userOnboarding",
    "id": "5",
    "attributes": {
      "visitEditorComplete": true
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "type": "userOnboarding",
    "id": "5",
    "attributes": {
      "visitEditorComplete": true,
      "chooseArticleComplete": false,
      "uploadImageComplete": false,
      "addCitedTextComplete": false,
      "viewContributionsComplete": false,
      "journeyComplete": false
    }
  }
}
```

Attribute | Type | Description
--------- | ---- | -----------
`visitEditorComplete` | boolean | The contributor has visited the editor.
`chooseArticleComplete` | boolean | The contributor has chosen a game, person, or company article.
`uploadImageComplete` | boolean | The contributor has successfully uploaded an image through the guided article workflow.
`addCitedTextComplete` | boolean | The contributor has successfully added article text with a citation.
`viewContributionsComplete` | boolean | The contributor has viewed their contributions.
`journeyComplete` | boolean | Response-only flag indicating that every onboarding task is complete.

### Contributor onboarding errors

HTTP status | Error code | Meaning
----------- | ---------- | -------
400 | `REQUEST_DATA_MISSING` | The JSON:API data or attributes object is missing.
401 | `NOT_AUTHORIZED` | Authentication is missing, or the current user cannot update this account.
409 | `ONBOARDING_RESOURCE_MISMATCH` | The body type or ID does not identify the resource in the URL.
409 | `ONBOARDING_NOT_ACTIVE` | The target user has no active contributor onboarding journey.
422 | `ONBOARDING_UPDATE_INVALID` | Attributes are empty or unsupported, or a value is not `true`.
422 | `ONBOARDING_STEP_INVALID` | A task is not part of the active onboarding definition.

## User preferences

`PATCH /user-preferences/{id}` updates one or more supported preferences.
Replace `{id}` with the user ID and use the same value for `data.id`. The
resource type is `userPreferences`.

Updates are partial and values must be JSON booleans. The response contains all
currently supported preferences with defaults applied. The same user or an
admin can update the resource. The endpoint has no `GET`, `POST`, or `DELETE`
action; clients obtain current preferences from `GET /users/{id}`.

> Disable onboarding email and editor reminders

```JSON
# PATCH /user-preferences/5
{
  "data": {
    "type": "userPreferences",
    "id": "5",
    "attributes": {
      "onboardingEmails": false,
      "showOnboardingReminders": false
    }
  }
}
```

> HTTP 200 response body

```JSON
{
  "data": {
    "type": "userPreferences",
    "id": "5",
    "attributes": {
      "onboardingEmails": false,
      "showOnboardingReminders": false
    }
  }
}
```

Attribute | Type | Default | Description
--------- | ---- | ------- | -----------
`onboardingEmails` | boolean | `true` | Whether onboarding emails may be delivered.
`showOnboardingReminders` | boolean | `true` | Whether dismissible onboarding reminders appear in the editor.

### User preference errors

HTTP status | Error code | Meaning
----------- | ---------- | -------
400 | `REQUEST_DATA_MISSING` | The JSON:API data or attributes object is missing.
401 | `NOT_AUTHORIZED` | Authentication is missing, or the current user cannot update this account.
409 | `USER_PREFERENCES_RESOURCE_MISMATCH` | The body type or ID does not identify the resource in the URL.
422 | `USER_PREFERENCES_UPDATE_INVALID` | Attributes are empty or unsupported, or a value is not a JSON boolean.

## Account activation

`POST /user-activations` activates an account using `email` and
`activationToken`. It returns the activated user with `200 OK`.

`PATCH /user-activations` requests a replacement activation email using
`email`. It returns `204 No Content`.

Both operations are unauthenticated.

## Email confirmation

`POST /email-confirmations` confirms a pending email-address change. Send
`unconfirmedEmail` and `confirmToken` in a JSON:API document. The user must
already be activated. Success returns the updated user with `200 OK`.

## Password reset

`POST /user-passwords` requests a password-reset email. Send `email`; success
returns `204 No Content`.

`PATCH /user-passwords` completes the reset. Send `email`, `password`, and
`passwordResetToken`; success returns `204 No Content`.

Both password operations are unauthenticated.
