# Verification and evidence model

## Evidence classes

The project keeps these claims separate:

- **Designed:** a documented boundary or intended behavior.
- **Implemented:** source exists for the behavior.
- **Built:** the identified source compiled in the identified environment.
- **Tested:** a defined test produced a recorded result.
- **Integrated:** the changed component worked at its real lab seam.
- **Owner accepted:** the owner reviewed the bounded result and limitations.
- **Independent:** a separate qualified party reproduced or assessed it.

The Quarterdeck evidence described here is author-produced unless explicitly
stated otherwise. AI review does not turn author-controlled work into
independent assurance.

## Verification pattern

1. Define the requirement and prohibited outcomes.
2. Identify the exact source and dependency baseline.
3. Build with warnings treated as errors.
4. Run positive, negative and fault-injection tests.
5. Verify the resulting machine state separately from process output.
6. Hash important inputs and outputs.
7. Preserve failures and corrections rather than rewriting history.
8. State what was not inspected or proven.

## Reuse-first evidence

V3 reused V2 evidence only when implementation, configuration, trust boundary
and expected behavior were unchanged. New evidence was required for:

- new V3 behavior;
- changed source or configuration;
- a changed integration seam;
- regressions affected by a change; or
- the final assembled V3 acceptance path.

This prevented a newer version from spending months re-proving unrelated V2
work while still requiring evidence for actual change.

## Independent AI-installer experiment

The planned isolated installer pattern separates three actors:

- a sealed package and runbook;
- a constrained AI executor inside a disposable range; and
- an out-of-band controller that owns snapshots, observes state, verifies file
  hashes and decides whether the attempt passed.

The AI cannot grade itself. Fault trials include missing prerequisites,
forbidden access, timeout/kill-switch behavior and rollback residue checks.
Even a successful result would demonstrate package usability and bounded
execution—not production authorization or independent human usability.
