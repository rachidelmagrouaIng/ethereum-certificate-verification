# Evidence and security review

These observations concern the supplied slides. They are not an audit of the unavailable original code.

## Creation authorization discrepancy

Slides 11, 13 and 15 describe director-only creation. The function body displayed on slide 15 checks duplicate creation but contains no `msg.sender` authorization check or displayed modifier. The full source is needed to determine whether the actual implementation enforces that requirement.

## Approval semantics

The shown approval functions check the designated caller and certificate existence, then set a boolean. They do not show a prerequisite approval, duplicate-approval rejection or revocation. “Double signature” here describes two authorized transaction approvals, not evidence of an off-chain signature aggregation scheme.

## Integrity and issuer trust

A matching SHA-256 fingerprint indicates matching document bytes under the hash's security assumptions. It does not independently establish the truth of the diploma's contents. A verifier must trust the institution's contract and the authority addresses. Changing PDF metadata or re-exporting a visually identical PDF can change its hash.

## Privacy and keys

Student addresses and hashes in a public chain can be observed and correlated. The student-access helper returns a boolean; it does not make public blockchain state confidential. The deck describes local wallet custody, but no source is available to assess actual key handling. Real credentials and private keys do not belong in this repository.

## Traceability and availability

The displayed struct includes a creation timestamp, not separate approval timestamps. Historical transactions may support further inspection, but no deployment or event evidence was supplied. Contract immutability alone does not guarantee the availability of the UI, RPC service or original PDFs.

## Claims intentionally left unquantified

The slides quote verification times, cost savings and fraud statistics without accompanying project measurements. This portfolio does not present those figures as validated results. The demo slide announces a live demonstration but contains no recording, screenshots or transaction identifiers.

## Questions for source recovery

- Are authority addresses distinct and nonzero?
- Does creation actually enforce director authorization?
- What hash format and input validation does the application enforce?
- How does Python request signatures from MetaMask?
- How are deployment identity, failed transactions and confirmations handled?
- Is there a policy for compromised keys, certificate revocation and correction?
