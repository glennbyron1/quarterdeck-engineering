# AI-assisted engineering

## Public-note provenance

This public repository is a curated copy of notes from Glenn Byron's private,
personal Quarterdeck R&D. AI was used to reorganize the material, improve its
clarity, flag unsupported wording and scan for information that should remain
private. Glenn decided what to publish and remains responsible for the final
claims. The private repositories—not this summary—retain the detailed source,
test and evidence history.

## Division of responsibility

Glenn Byron provided the architecture, objectives, system boundaries, lab
environment, risk decisions, approvals and acceptance judgments. AI tools were
used to help:

- organize research and requirements;
- draft and revise documentation;
- generate bounded code and tests;
- review changes and identify possible defects;
- troubleshoot cross-system failures;
- compare design alternatives; and
- prepare repeatable runbooks and evidence summaries.

## Controls on AI use

- AI suggestions were treated as untrusted until supported by source or
  observed execution.
- Destructive or security-sensitive actions required explicit scope and owner
  approval.
- Exact artifacts were hash-bound when transferred between environments.
- A separate controller verified system state rather than trusting an AI's
  success statement.
- Failures and uncertainty were preserved.
- AI-assisted work was labeled author-produced, not independent assurance.
- Private keys, PINs, PUKs and recovery secrets were kept outside source and
  evidence repositories.

## Why AI was useful here

The project spans Windows, AD, PKI, PIV devices, networking, virtualization,
storage, code, testing and documentation. AI accelerated cross-domain analysis
and helped maintain continuity across a large body of work.

The goal was not autonomous code generation. The goal was a disciplined human–AI
engineering loop in which the human retained authority and the machine helped
surface inconsistencies, generate bounded artifacts and test assumptions.

## Known limitation

Multiple AI reviewers do not constitute independent review when they operate
from author-supplied materials under the author's control. Independent evidence
requires a separate qualified operator or assessor with its own authority and
acceptance process.
