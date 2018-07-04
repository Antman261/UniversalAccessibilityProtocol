# How to use schemas

Piece together a device specification from the contents of `actions`, `actionable_nouns`, and `structures` while adhering to the UAP specifications:

1. Only `actions` should be used in a `directives` array. This specifically excludes `actionable_nouns`.
2. `actionable_nouns` should be listed within a suitable structure such as `destinations`, to provide additional context.
3. All arrays may contain integers if it makes sense to do so as an `action` or `actionable_noun`. However, aim to keep all integers in their closest relevant structure, such as in `destinations` if pertaining to levels/floors in a lift.
5. Every device's UAP specification must include a `directives` element exactly once.
