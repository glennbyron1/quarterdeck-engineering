# Demonstration and interview walkthrough

This is a safe, ten-minute presentation plan. It demonstrates engineering
thinking without exposing the private lab.

## 1. Problem — one minute

Explain that physical credential issuance crosses HR, IT, directory, CA,
hardware and user boundaries. The project is about managing that chain—not
creating another CA.

## 2. Architecture — two minutes

Use the interactive diagram to show:

- customer-controlled AD and AD CS;
- Quarterdeck's workflow and audit boundary;
- the constrained local broker;
- private-key operations inside the physical device; and
- separation between approval, external action and evidence.

## 3. Version progression — two minutes

- CAC-program established the technical foundation.
- V1 proved the application concept.
- V2 proved the integrated lab path.
- V3 corrected ambiguity, recovery and commissioning boundaries.
- V4 tested simplification and stopped on a stale-session authorization flaw.

## 4. One failure — two minutes

Describe the JEA stale-session test. Emphasize the decision to stop and require
per-request service authorization rather than weaken the requirement.

## 5. Verification — two minutes

Explain signed source, hash-bound transfers, protected Windows builds,
negative/fault tests, separate state observation and honest evidence labels.

## 6. Close — one minute

State the demonstrated strengths:

- systems integration across organizational and technical boundaries;
- security architecture and fail-closed design;
- requirements and verification discipline;
- recovery and operational thinking; and
- effective, controlled use of AI in engineering.

## Recording rules

- Use synthetic names only.
- Do not show hypervisor, DNS, IP, certificate or account details.
- Record a prepared diagram or sanitized mockup—not live administration.
- Do not display private repository URLs or browser history.
- State the lab/non-production boundary verbally and on screen.
