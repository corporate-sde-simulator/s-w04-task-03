# PR Review - Document approval workflow FSM (by Amit Kumar)

## Reviewer: Pooja Reddy
---

**Overall:** Good foundation but critical bugs need fixing before merge.

### `ApprovalWorkflow.java`

> **Bug #1:** State machine allows transition from REJECTED back to APPROVED but should only allow DRAFT
> This is the higher priority fix. Check the logic carefully and compare against the design doc.

### `StateTransition.java`

> **Bug #2:** Parallel approval does not wait for all approvers and marks approved after first approval
> This is more subtle but will cause issues in production. Make sure to add a test case for this.

---

**Amit Kumar**
> Acknowledged. I have documented the issues for whoever picks this up.
