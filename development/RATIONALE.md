# Why the Producer Pattern has this shape

Living design rationale · updated October 16, 2026. This repository authors a
candidate pattern; it has not automatically adopted or installed that pattern.
This document explains the current reasoning, tradeoffs, and revisit triggers.
It is not an activity log or a claim that every design direction is approved.

Keep four claims distinct: **stored** means preserved in a file; **decided** means
an explicit choice has been made; **implemented** means the behavior exists;
**verified** means relevant evidence demonstrates it. A requirement can be accepted
while its implementation remains open. Tracked-by-default is accepted; the entire
package is not thereby approved. The request-folder/link implementation is now
authorized separately; implementation and verification still need their own evidence.

The operational contracts are [PATTERN.md](../pattern/PATTERN.md),
[MODELS.md](../pattern/MODELS.md), and [STATE.md](../pattern/STATE.md). This public
rationale distills design decisions, alternatives, and regression cases. Source
conversations and internal references remain private. Public contracts must be
understandable without access to those materials or provider memory.

## R1 — One accountable conversation, without a forced organization

**Problem:** Delegation can leave the user assembling worker reports, or turn a
simple project into departments and hierarchy before those solve any real problem.
**Current direction:** One folder normally has one project producer. It stays in
conversation, interprets intent, coordinates execution, judges returns, requests
concrete rework, and accepts the integrated outcome. This is the candidate contract,
not a claim of successful adoption. Explicit child producer scopes remain possible.
**Why:** Accountability belongs to the outcome; team count, worker count, role,
execution mechanism, model capability, and state mode are separate choices.
**Consequence:** No fixed org tree, department registry, or mandatory network setup.
See [PATTERN.md](../pattern/PATTERN.md). **Revisit:** recurring ownership or integration friction
shows a specific missing responsibility that a bounded additional scope would solve.

## R2 — Protect judgment and conversation from execution/bookkeeping

**Problem:** A producer doing every small implementation or state update can drift
back into being the worker, consuming its attention and strongest model capacity.
**Current direction:** Producer is strictly non-worker. It answers discussion and
critically reads selected primary evidence/artifacts for judgment. Workers execute;
Small clerks map broad material; a Small recorder performs routine state I/O.
**Why/tradeoff:** This preserves focus but requires actual delegation/persistence
support; unavailable capability must be disclosed, not hidden by a silent role switch.
**Consequence:** Capability tiers describe reliability/reasoning needs, not brands,
cost guarantees, or selections made by a prompt label. Host model/effort mappings
must be actual or unknown. See [MODELS.md](../pattern/MODELS.md) and [PATTERN.md](../pattern/PATTERN.md).
**Revisit:** observed host limits or workload evidence justify a consciously chosen
operating-mode change; they do not create a permanent direct-execution exception.

## R3 — Retain commitments by default, preserve original intent

**Problem:** Short/creative work can still carry commitments, corrections, and
partial completion that must survive tomorrow; project type is a poor retention test.
**Accepted decision, October 16:** Use tracked state by default, with lean as an
explicit option. This supersedes choosing retention mode by project type. Lean
omits a complete-backlog promise; creative work does not imply lean mode.
Existing trackers stay canonical.
**Why/tradeoff:** Small persistence receipts add overhead, but prevent entrusted work
and tiny steering from disappearing. Whole exact user messages remain separate
from interpreted titles, scope, acceptance, and decisions; attachments matter too.
**Consequence:** Independent outcomes are independently visible, with sources and
history intact. Status is not liveness, completion is not release, and files do not
wake agents. See [STATE.md](../pattern/STATE.md). **Revisit:** evidence that a bounded exploration
needs a different retention promise; do not silently cancel work when changing mode.

## R4 — Relationships must support several orientations

**Requirement:** Projects may coordinate with peer projects. Relationships must
support different ownership and dependency arrangements without mandating a workflow.
**Current design:** Separate source/provenance, optional grouping/decomposition,
explicit required completion dependencies, and ownership handoffs. Directed links
can express these without a universal parent tree, graph database, or central registry.
**Why:** Shared source or a parent label cannot establish every completion rule.
Informational backreferences may be reciprocal; only real blocking edges need
cycle/unresolved-dependency checks. A producer can derive required links within scope.
**Consequence:** Flat request bundles can support graph-shaped relationships;
optional umbrellas are useful only for real whole-scope commitments. See
[REQUEST_RELATIONSHIPS.md](REQUEST_RELATIONSHIPS.md). **Revisit:** a concrete
scenario cannot be represented without forcing ownership or completion into a tree.

## R5 — Preserve the four-outcome restart truth across ownership boundaries

**Regression story:** One message asks for a folder, research, a new repository,
and a complex app. The first three finish; another project's producer acknowledges
the app deliverable. Tomorrow the answer must remain “three complete; the fourth
waits on that owner,” with original context and last verified status/time intact.
No untying, reopening, or rebundling completed siblings should be necessary.
**Current design:** Receiver owns its requests and execution; source retains its
commitment and judges the agreed returned outcome, without mirroring a remote task
tree. Project/request IDs are identity; current roots/paths are locator hints.
**Why/tradeoff:** Ownership stays clear while source observations may be stale.
Attempted send, acknowledgment, execution, return, and acceptance are distinct.
**Consequence:** Acknowledged external supervision lets the source go offline with
a durable waiting commitment; it need not manage receiver descendants. It retains
acceptance authority, with no promised wakeup. Unacknowledged sends do not qualify.
Cancellation/removal preserves a non-success/revised-scope disposition, not fabricated
success. Details and the restart table are in the [relationship design](REQUEST_RELATIONSHIPS.md).
**Revisit:** lost acknowledgments, inaccessible source content, moved locators, or
contradictory ownership expose a specific resolution/transport requirement.

## R6 — Standardize request folders without losing recovery guarantees

**Problem:** A flat request file can preserve state but leaves request-local assets
and evidence at separate locations. Relocating the request then requires several
references to remain consistent.
**Accepted direction, October 16:** Standardize one folder per actionable request
and implement flexible ownership/dependency links.
Keep seven lifecycle states mapped to pending/working/archive, exact shared source
bundles, stable project/request identities, and distinct relationship meanings.
**Why/tradeoff:** Local assets/evidence should travel with a request, while shared
originals and large outputs remain canonical through references. Moves require
resolution, collisions/stale-write protection, retry identity, journaling, and repair;
no multi-file atomicity or automatic migration is implied.
**Consequence:** A versioned helper now implements this direction; disposable
verification evidence is recorded in [DESIGN_NOTES.md](DESIGN_NOTES.md). Legacy stores remain intact and are never silently converted. Transport, liveness,
authentication of supplied proof, and foreign writes are outside the helper.
The [storage comparison](REQUEST_STORAGE_COMPARISON.md) explains the alternatives.
**Revisit:** preservation, recovery, dependency, or ownership fixtures expose a gap;
revise the bounded implementation, not the accepted independent-outcome requirement.

## R7 — Keep the reasons durable, current, and revisable

**Requirement:** Preserve the reasons behind formative decisions so future work
can evaluate a change without repeatedly rediscovering earlier tradeoffs.
**Current practice:** This is the canonical public explanation of WHY; contracts
define behavior, detailed design docs explain mechanisms, and
[DESIGN_NOTES.md](DESIGN_NOTES.md) records validation scope and open gates.
**Why/tradeoff:** A coherent explanation is more useful than a growing transcript,
but refactoring must not erase the evidence or reasons for changed decisions.
**Consequence:** Repository authors read relevant rationale before changing design;
this is authoring guidance, not automatic installation of producer behavior here.
**Revisit:** new formative evidence changes a decision, exposes a contradiction,
or shows that guidance is unreachable or no longer improves behavior.

## R8 — Separate the installed method from its workshop

**Requirement:** Install only the method. Public development documentation and
tests support maintenance but are not target-project installation payload.
**Chosen layout:** Keep one repository to prevent rationale and method drifting,
but isolate a self-contained `pattern/` package from `development/` rationale
and tests. The layout is an implementation choice. Root README routes each
audience explicitly.
**Why/tradeoff:** The workshop remains shareable and refactorable while an agent can
download/install just the method. `pattern/manifest.json` selects copied payload;
guides and authoring AGENTS are not target instructions. No pattern is installed here.
**Consequence:** Generic rationale and tests remain public and outside the
installation payload. Raw conversations and internal references remain private.
**Revisit:** a boundary check reveals an external package dependency, accidental
copying of authoring material, or unintended publication of private evidence.

## Maintain this explanation

At a material design choice, update the relevant topic rather than append every
conversation. State context, current direction/status, why/tradeoff, affected contract
or design reference, and a concrete scenario that should still work. Label uncertainty
as hypothesis/open. Ordinary status chat or a hunch does not create universal policy.
Refactor for coherence; preserve dated changes and superseded reasoning in a short
history or linked design record rather than silently rewriting the past.

Preserve source evidence privately without rewriting originals. Later steering
gets a dated addition; current contracts and dated decisions/supersessions control.
Publish distilled reasoning rather than verbatim conversations or internal-source
pointers. Public documentation must stand on its own.

## Initial decision history — October 16, 2026

- Accepted tracked-by-default with lean optional, superseding project-type defaults.
- Preserved the user's independent-outcome/peer-ownership restart requirement;
  refined the candidate around flexible links and acknowledged external supervision.
- Separated installable method from workshop material after the explicit boundary
  request; retained one repository with an isolated package and manifest copy list.
- Established a living rationale to retain decisions, alternatives, and revisit triggers.
- Selected and implemented request folders with typed links, superseding the earlier
  flat-file design; host mappings and real adoption remain separate gates.
- Established a public/private authoring boundary: generic rationale and tests are
  public; exact conversations and internal reference material are retained privately.
