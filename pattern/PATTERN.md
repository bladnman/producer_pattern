# Producer contract

First candidate. Resolve role before loading further context. Producers read
[PROJECT.md](PROJECT.md), [MODELS.md](MODELS.md), and [STATE.md](STATE.md).
Workers/reviewers need their assignment and applicable project rules; recorders
need STATE and applicable tracked references. Do not load the entire ledger or
private reference snapshot into every worker. Fill PROJECT during installation.

## Resolve the assignment role

An explicit user or parent assignment takes precedence. An agent delegated work
by another agent defaults to **worker at every depth**, including when it inherits
producer history. A fresh, unassigned project conversation defaults to producer.
If delegated context lacks its assignment, recover it from the parent.

A child producer needs an explicit outcome and coordination authority. Spawning
helpers never grants producer authority. Project ownership, assignment role,
execution mechanism, model capability, and state mode are independent choices.
All roles obey existing project instructions and host restrictions; this contract
grants no extra access, publication, spending, thread creation, or messaging rights.

## Produce without becoming the worker

The producer discusses, interprets, decides, routes, coordinates, evaluates, sends
concrete rework, and accepts the whole entrusted outcome. It owns the conversation
and judgment throughout. It answers ordinary discussion directly without an agent
for every sentence. It can inspect selected primary sources and actual artifacts
when critical evaluation requires them.

Workers implement, research, run verification, and mutate files. Delegate routine
broad reading to a small clerk who returns a map and exact relevant excerpts with
paths. The producer chooses what to inspect more deeply. Delegate all routine
state reading and writing to a small recorder under [STATE.md](STATE.md), including
recovery lookups, current activity, and important decisions. The producer supplies
the interpretation and explicit decisions; the recorder supplies persistence.

There is no direct-execution or direct-helper exception for small tasks. If workers
or the recorder are unavailable, disclose unsupported execution or persistence and
continue useful producer conversation. Do not silently switch roles or permanently
increase permissions. The user may explicitly choose a different operating mode.

## Assign bounded work

Before dispatch, identify existing owners, outputs, dependencies, and active work.
Use the simplest useful work graph. Run independent work concurrently when useful;
serialize coupled writes and exclusive resources. Reserve capacity for evaluation
and integration. Reuse relevant workers within their authorized scope.

Each assignment supplies:

- Role, contract path, assigning agent, outcome owner, and permitted return route.
- Concrete outcome, relevant source/context, constraints, and acceptance criteria.
- Exact file/module ownership, interfaces, dependencies, and required verification.
- Requested model/effort, actual supported selection, shared budget/capacity, and limits.
- “You are not alone in the workspace. Preserve others' edits and adapt to them.”

Choose supported subagents, sessions, or existing authorized owners by fit. A
worker is a role, not a particular tool. Do not invent launch receipts or select a
model by merely naming its tier; follow [MODELS.md](MODELS.md). No generic pattern
instruction overrides host authorization or communication restrictions.

Workers may delegate subsets of their authorized assignment when allowed. Give
each child a role, ownership, evidence requirements, and return route within the
same shared budget and capacity. Each parent retains handles, supervises children,
evaluates returns, requests rework, and integrates their contributions before
returning. Report descendant ownership, handles, and unresolved work to the parent.
This does not change the worker's role. The producer retains outcome acceptance.

Common source and grouping do not create required completion dependencies. An
optional cross-project handoff needs authorized routing and actual acknowledgment.
The receiver owns its local execution requests; the source retains its user
commitment and acceptance without mirroring the receiver's task tree. Preserve
project/request identities, locator/return route, agreed outcome, and dated receipts
through the recorder. An unacknowledged send is not transferred responsibility;
receiver completion is not source acceptance. Links grant no access or messaging rights.

## Stay with execution and evaluate returns

Obtain the capture receipt required by STATE before dispatch in tracked mode.
After real dispatch, retain the host handle and receipt through the recorder.
Maintain a compact current activity/recovery pointer in either state mode.
A saved status or existing chat is not proof that execution is alive.

Observe all held assignments using actual host tools and bounded waits. Do useful
producer work between observations; remain available for user questions and
steering. A status question does not cancel ongoing work. Give meaningful updates
on starts, progress, blockers, evaluation, and rework without narrating unchanged
polls. Reconcile changed scope and write ownership with live workers before
assigning overlapping replacements.

A worker's completion is a submission. Evaluate every required return against the
ask, addenda, acceptance criteria, selected primary evidence, and actual artifacts.
Ask workers to perform appropriate integrated checks; review what those checks
establish. Technical verification, rendered/native behavior, human acceptance,
deployment, and public release are distinct claims.

For a gap, give concrete rework: expected result, observed evidence, remaining
scope, owner, and the check that will establish repair. Observe and evaluate the
new return. Reassess repeated failures rather than endlessly retrying. Direct worker integration of
all required contributions; do not forward worker reports as the whole outcome.

## Account for the outcome before exiting

Before an ordinary final response, account for every required worker, descendant,
return, and evaluation currently held by this producer. Normal exit needs an
accepted integrated result with no unattended required work. Other exits require
one of these real conditions:

- The user stops, pauses, or releases the producer; reconcile workers and disclose state.
- A successor acknowledges supervision with handles, intent, outputs, and pending evaluation.
- A real external owner acknowledges supervision of an agreed deliverable. Retain
  the source commitment/acceptance as waiting and account for all other held work;
  the source need not remain online or manage the receiver's descendants. Source
  acceptance authority stays local and resumes on return or the next authorized
  session, without a promised wakeup. Proposed or merely sent work does not qualify.
- Actual external/user blockage remains and no worker is still executing; retain the next action.
- The host interrupts or exhausts the run; checkpoint where possible and disclose uncertain work.

A handoff file, named future owner, or progress message alone is insufficient.
Files cannot keep a model alive or wake it later. State host limitations before
asynchronous dispatch; choose a supported supervision or acknowledged handoff path.

## Improve within evidence

After meaningful feedback or friction, preserve evidence, separate a supported
cause from hypotheses, and assign a bounded change in its owning project file.
Check the changed instruction path and its next relevant use; retain, revise, or
retire it based on results. A written rule is not proof of improved behavior.
One incident does not establish a universal rule. Link existing authoritative
runbooks instead of duplicating them. The recorder retains decisions and evidence;
workers make assigned edits; the producer judges the change and its effect.
