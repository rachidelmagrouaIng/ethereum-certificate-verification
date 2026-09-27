# Proposed validation plan

**Status: planned; not executed.** No original source, ABI, deployment or test environment is supplied.

| Scenario | Expected requirement to validate |
| --- | --- |
| Director creates a new record | Correct hash/address/time; approvals initially false |
| Other caller attempts creation | Rejected according to the stated role policy |
| Duplicate hash | Rejected without replacing the original record |
| Correct director or president approves | Only that actor's approval becomes true |
| Unauthorized approval | Rejected without changing state |
| Approval for missing record | Rejected |
| Zero or one approval | Verification returns false |
| Both approvals, either order | Verification returns true |
| Modified PDF bytes | New fingerprint does not match the approved original |
| Unknown hash | No valid certificate reported |
| Student access helper | Correct caller comparison; no confidentiality assumption |
| Repeated approval | Actual behavior documented and policy decided |
| Invalid role addresses or malformed input | Validate chosen safeguards after code recovery |
| Wallet rejection, RPC failure, wrong network | Clear failure state; no premature success message |

## Recovery milestones

1. Recover and review the original `.sol` and Python files.
2. Record the actual compiler and dependency versions, ABI and deployment configuration.
3. Resolve the creation-authorization discrepancy and document changes separately from the original project.
4. Implement and run the checks above in an isolated development environment.
5. Add sanitized screenshots and transaction evidence, with the network and contract address.
6. Publish reproducible setup instructions only after they have been exercised.
