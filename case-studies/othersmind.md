# Othersmind

**Turning construction context into structured, evaluated work.**

Implementation prototype · source private · September 2026 snapshot

## The problem

Operational information arrives in different forms and at different times. A useful system needs to connect that context to work someone can inspect, approve, or correct. Generating an answer is only one step.

## What exists

The implementation includes agent execution, result evaluation, retry and escalation paths, request-triggered cascade dispatch, model selection, and optional budget controls. Draft approval state is persisted. Scheduled endpoints require an external caller; this main snapshot does not include a built-in scheduler. A separate product-UI branch explores a more explicit signals-and-approvals interface.

```text
operational context
        ↓
structured signal / task
        ↓
agent execution → result evaluation
        ↑                ↓
       retry       escalation / review
                         ↓
                 human decision
```

This diagram describes the implemented workflow concept. It is not a map of a verified production installation.

## The engineering choices

- Separate producing a result from deciding whether it is acceptable.
- Use bounded retries and escalation instead of assuming the first response succeeds.
- Treat model choice and execution cost as explicit system concerns.
- Keep proposed changes and human approval visible.

The system includes AI model integration, but integration code alone does not establish live reliability or quality across real operational cases.

## What was checked

The main-branch TypeScript check and offline test suite passed during the September 2026 review: 47 test files and 458 tests. Those checks provide evidence for covered code paths, including mocked failure behavior. They do not establish customer adoption, production uptime, live model quality, or reliable outbound communication.

## What is unfinished

The newer approval UI calls edit, reject, and send procedures that are absent from the backend in that branch. Main supports a persisted approval decision; it should not be described as a completed approval-to-send workflow. The branch work needs integration and end-to-end verification before it becomes a credible live demonstration.

Customer-specific operational material is excluded from this public note. A demonstration should use synthetic projects, documents, people, and commercial figures.

## The next useful experiment

Take one synthetic operational signal through execution, evaluation, a deliberately failed result, escalation, and a visible human decision. Show the intermediate states and the failure, not only a polished final answer.

[Back to the lab](../README.md)
