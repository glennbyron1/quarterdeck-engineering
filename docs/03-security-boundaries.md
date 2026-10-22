# Security and trust boundaries

## Authority model

Quarterdeck may coordinate an action only after the organization has established
the authority, policy, roles, hardware and trust path required for that action.
It must not weaken CA templates, grant itself broader directory rights, alter
domain policy, initialize trust roots or bypass approval controls merely to make
an operation succeed.

## Private-key boundary

- Quarterdeck has no certificate-authority signing implementation.
- CA signing is performed by customer-controlled CA software and its configured
  cryptographic provider.
- Credential keys are generated and used inside the exact physical PIV device.
- Quarterdeck may handle public requests, certificates, chains, hashes and
  verification results, but never a CA or credential private key.
- PINs, PUKs, management keys, passwords and unrestricted authentication tokens
  are not workflow data.

## Identity and authorization

- Production identity comes from Windows and Active Directory—not a second
  Quarterdeck user directory.
- Roles are mapped through explicit directory groups.
- Sensitive decisions are enforced at the application/service boundary, not
  merely hidden or disabled in the browser.
- Caller-supplied names, roles or SIDs never replace a trusted Windows token.
- Account disablement, role removal, stale directory state or failed resolution
  must deny the next action.

## Physical authenticator boundary

The intended production path accepts only approved physical PIV devices. A
software token, TPM virtual smart card, emulator or redirected device cannot be
silently treated as an equivalent credential. Simulation is useful for workflow
testing, but it cannot produce physical-device evidence.

## External effects and ambiguity

The system distinguishes:

1. intent recorded locally;
2. command dispatched;
3. external authority accepted or rejected the command; and
4. result persisted locally.

If a connection is lost between those steps, the result is unknown—not an
automatic failure and not permission to retry. Recovery observes the same
operation and requires exact evidence before resolving it.

## Removability

Quarterdeck is intended to be a removable control layer. Removing it must not
destroy the organization's directory, CA, trust roots, keys, cards,
certificates or normal administrative paths.
