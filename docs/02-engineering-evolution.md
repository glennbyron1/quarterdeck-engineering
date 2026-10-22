# Engineering evolution

## CAC-program — foundation

The public CAC-program explored Windows smart-card authentication, PKI,
directory integration, networking and credential behavior. It provided the
technical foundation and exposed the difference between making authentication
work once and managing a defensible credential lifecycle.

## V1 — prove the application idea

V1 implemented the first workflow and authorization model. It established that
the lifecycle could be represented in software and gave later versions a
concrete implementation reference.

Disposition: complete and frozen historical reference.

## V2 — prove the integrated lab path

V2 focused on a live Windows lab. It combined a Razor application, SQLite,
Windows/AD authorization, a constrained broker, disposable AD CS trust,
physical PIV operations, Windows logon, revocation, backups and recovery.

Important lesson: a successful end-to-end lab result does not automatically
make deployment, recovery, usability or evidence boundaries simple.

Disposition: complete author-produced lab milestone, not a production release.

## V3 — correct what V2 exposed

V3 was explicitly **not** a clean-sheet rewrite. It reused V2 when behavior and
boundaries were unchanged, then concentrated on approved differences:

- clearer HR intake and IT account-preparation handoff;
- exact request and subject binding;
- approval, verification, issuance and delivery as separate facts;
- durable intent before an external action;
- explicit unknown/ambiguous outcomes;
- recovery against independently retained simulated external truth;
- stronger commissioning and protected-state handling; and
- an isolated AI-installer exercise judged by a separate controller.

V3 produced extensive source and protected-Windows test evidence, but it did
not finish the final installed LiveHost, authenticated HR request and one
assembled representative lifecycle. It remains preserved and incomplete.

## V4 — simplify and challenge the control channel

V4 explored a smaller administrator-tool direction and constrained execution
through Windows Just Enough Administration. The experiment found a decisive
weakness: an already-open JEA session could retain authorization after its AD
role was removed.

The result was not hidden or designed around. V4 was paused with a correction:
JEA may constrain commands, but a compiled service must authorize every request
using the actual client token and current directory state.

Disposition: preserved concept and bounded experiment; Phase 0 remains open.

## Versioning rule

Each version is a stepping stone. Later versions may reuse proven behavior, but
they cannot inherit an unproven claim merely because an earlier version had a
similar component. Conversely, unchanged integrations are not repeatedly
rebuilt simply to make a newer version appear more complete.
