# Problem, users and scope

## Problem statement

Small organizations may need phishing-resistant Windows authentication but lack
the staff and process maturity of a large credential office. The difficult part
is not merely generating a certificate. It is maintaining a trustworthy chain
from a real person and an authorized request to the exact physical credential,
the correct Windows identity and a recoverable evidence trail.

The research question was:

> Can a small, removable workflow system coordinate existing Windows, directory,
> certificate-authority and physical-device capabilities without becoming a new
> source of identity, trust or private-key custody?

## Intended operating model

The smallest useful setting is a department where one person may wear multiple
roles, while larger organizations can separate them:

- HR or another verifier establishes the person and approves the exact request.
- IT creates or validates the account through existing administrative tools.
- An authorized operator prepares the physical card or PIV USB device.
- The cardholder privately establishes the final PIN.
- Existing AD, AD CS and Windows policy provide directory and trust authority.
- Quarterdeck records state, authorization, results and recovery work.

The preferred model separates request preparation from final identity approval.
Small-site self-approval must be explicit, limited and auditable rather than
quietly treated as equivalent to two-person control.

## In scope for the prototypes

- Physical PIV lifecycle workflow.
- Windows identity and role resolution.
- Existing AD and AD CS orchestration.
- Exact request, subject and device binding.
- Windows smart-card authentication proof.
- Revocation and disabled-account behavior.
- Durable workflow/audit state, ambiguity and recovery.
- Backup, restore, teardown and lab recast.
- Installer safety and evidence provenance.

## Out of scope or deliberately deferred

- Operating as a CA or storing CA/credential private keys.
- Replacing Active Directory or customer policy.
- Production accreditation or a claim of federal PIV conformance.
- Universal device interoperability.
- A completed commercial product, support organization or licensing system.
- Phone-based MFA as a replacement for the PIV path.
- Production CardLogix integration without the actual supported hardware,
  middleware rights and acceptance evidence.

## Why this matters

The project is less about creating another certificate-enrollment button and
more about systems integration across organizational and technical boundaries:
people, approvals, Windows identity, cryptographic hardware, PKI, recovery and
evidence must agree before the result can be trusted.
