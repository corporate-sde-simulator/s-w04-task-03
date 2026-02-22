# FINSERV-4150: Investigate document approval workflow getting stuck

**Status:** In Progress · **Priority:** High
**Sprint:** Sprint 26 · **Story Points:** 8
**Reporter:** Sunil Patil (Process Lead) · **Assignee:** You (Intern)
**Labels:** `backend`, `java`, `workflow`, `investigation`
**Task Type:** Code Debugging

---

## Description

The document approval workflow gets stuck when multiple approvers act simultaneously. Documents that should be approved end up in limbo, and some rejected documents still move to the next stage.

**DEBUGGING task — no hint comments in the code. You must investigate.**

## Symptoms

- Document submitted for 3-person approval chain: first approver approves, second rejects (should stop the chain) but document continues to third approver
- When two approvers click simultaneously, the state becomes `approved-rejected` (invalid)
- Workflow history shows transitions that violate the state machine (e.g., `draft` -> `approved` skipping `pending_review`)

## Acceptance Criteria

- [ ] Root cause found and fixed
- [ ] All unit tests pass
