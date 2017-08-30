# <a name="articles_intro"></a>Articles

Use this feature to get mixed collections of game, company and people articles.

### Default response attributes

Attribute | Description
--------- | -----------
display_title (str) | The main article title
sort_title (str) | Removes 'The' for company and game names; puts family name first for people
slug (str) | Unique parameterized display_title used for friendly URLs
description (str) | Article summary text
last_submitted_at (time) | Date and time last submitted for peer review
last_reviewed_at (time) | Date and time last peer reviewed
last_review_outcome (str) | Outcome of last peer review
last_review_comments (str) | Comments from last peer review
published_at (time) |  Date and time published
status (str) | Publishing status

### Relationships

Relationship | JSON API type
------------ | -------------
primary_images | images
created_by | users
last_reviewed_by | users
