# Failures and design lessons

The most valuable outputs were often the points where a test stopped the plan.

## Stale JEA authorization

An operator was removed from its mapped AD role while retaining an open JEA
session. The next JEA command was still accepted because the existing Windows
session/token retained its earlier authority.

**Lesson:** JEA can constrain commands, but it cannot be the final authorization
authority. A compiled service must validate the real caller and current role
state for every request.

## Ambiguous external results

A connection can fail after an external system accepts a command but before the
local application records success.

**Lesson:** retry is unsafe until the original operation is reconciled. Durable
intent and exact operation identity must exist before dispatch.

## Restoring only local state

Restoring an older application database can erase the local memory of an action
that an external authority already accepted.

**Lesson:** recovery cannot treat the restored database as the sole source of
truth. V3 used a separate simulated authority journal and conflict tombstones to
exercise asymmetric restore behavior.

## Installer replacement and commissioned state

A stopped component replacement could damage or ignore separately commissioned
workflow/submission-key state.

**Lesson:** installers must recognize and preserve protected state, refuse
unknown commissioned layouts before mutation and roll back transactionally.

## Scope and progress visibility

V2 produced stronger integrated results, but long campaigns made it difficult
to see what remained. V1's simpler phase presentation was easier to follow.

**Lesson:** technical depth and human visibility are separate requirements.
Future work should maintain one plain-language map of completed, active,
blocked, deferred and disproven work.

## Hardware assumptions

One physical YubiKey path cannot prove every PIV card, reader, middleware,
firmware or algorithm combination.

**Lesson:** hardware interoperability is an acceptance matrix, not a generic
claim based on one successful token.
