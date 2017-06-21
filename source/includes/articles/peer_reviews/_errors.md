## <a name="peer_reviews_errors"></a>Errors

Errors specific to peer reviews of articles.

HTTP code | Error code | Pointer | Title
--------- | ---------- | ------- | -----
401 | PEER_REVIEW_SUBMISSION_DECLINED | | Peer review submission can only be made by the article creator.
401 | PEER_REVIEW_OUTCOME_DECLINED | | Peer review cannot be made by article creator.
400 | PEER_REVIEW_ALREADY_PUBLISHED | | The article has already passed peer review.
400 | PEER_REVIEW_OUTCOME_BLANK | `last_review_outcome` | Review outcome must be present.
400 | PEER_REVIEW_OUTCOME_INCLUSION | `last_review_outcome` | Review outcome must be an accepted value.
400 | PEER_REVIEW_COMMENTS_BLANK | `last_review_comments` | Review comments must be present.
400 | PEER_REVIEW_COMMENTS_TOO_LONG | `last_review_comments` | Review comments cannpt be longer than 800 characters.
