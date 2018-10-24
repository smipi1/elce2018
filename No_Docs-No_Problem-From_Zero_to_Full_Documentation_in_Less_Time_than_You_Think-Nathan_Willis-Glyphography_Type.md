# No Docs? No Problem! From Zero to Full Documentation in Less Time than You Think - Nathan Willis, Glyphography Type

## Structuring a roll-out

Identify target readers
Mine issue tracker for topics
Define per unit objectives (concrete terms)
Collect outside resources and links before writing
Write and review outlines before beginning with content

## Documentation as an API

APIs are designed to be consumed
* Assess users needs

APIs distinguish between enternal and external

APIs define multiple ways to access core functionality

APIs reflect design decisions
* I.e. documents should reflect design of your code
* Don't structure based on teams: Leaves user confused
* Don't document based on history

APIs return helpful error messages

## Tips from trenches

Write everything in plain-text format (as long as humanly possible)
Do repeat yourself, just do it exactly
Repeat your external links too
Plan to have no FAQ page (Detailed TOC instead)
Be prepared for people to start reading in the middle
Do style checking in the editor, not in the test suite (E.g. grammar)

## Documentation and CI

Reviews:
* Include full read-throught (periodically)
* Include outside reviewers and non-native-language readers

Repositories: different documentation units may need to be separate

Tests
* YES: build errors, syntax and spelling, embedded content, terminology
* NO: grammar & style, external link reachability

Deployment
* Depends on unit and audience
* Reference material should never be in an undefined state
* User guides and tutorials can get updated regularly, assuming you review

**There is no substitute for a top-down masterplan**

## Discussions

Don't publish an incomplete Doc

