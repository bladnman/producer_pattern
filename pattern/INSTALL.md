# Install the candidate

On an adoption request, perform reversible local setup without another routine
confirmation. Reading alone is not adoption. Preserve existing authority, edits,
canonical trackers, and unfinished work. No publication, request migration, app
launch, scheduler, or executable installer is part of this setup.

## Select and copy only the payload

[manifest.json](manifest.json) is the single authoritative copy allowlist. Its paths
are relative to this package; preserve each selected path under the target project's
`.producer/`. Copy `base_files` in every mode. Add `tracked_files` only when selecting
a new bundled tracked store. Everything else is excluded; do not recursively copy
the repository or package directory. README, INSTALL, and manifest are guidance,
not payload. A temporary staging clone is optional transport only.

1. Inspect the target's actual startup instruction entrypoint and referenced rules.
   Identify root, existing owners/tracker, and real delegation, model, effort,
   context, observation, and return capabilities. A tier label proves no selection.
2. Have an installation worker copy the selected manifest files. Fill the installed
   PROJECT.md from actual project context, leaving unknowns visible. The producer
   decides mode/mappings; the worker records them. Tracked is default; lean optional.
   An existing canonical tracker uses the contract without creating a second store.
3. For a new bundled tracked store, have the recorder run
   `python3 <target>/.producer/tools/requests.py init`. It creates/preserves config
   schema 1 and initializes request-store schema 2 with a stable project ID.
   Record the actual init receipt in PROJECT; do not hand-invent identity or
   convert legacy stores. Config is generated setup, not an extra copied file.
   Lean needs no helper; optional new lean config uses `"record_mode":"lean"`.
   Preserve existing config keys. Switching tracked to lean first requires
   reconciling commitments, live assignments, and pending evaluation; preserve the
   ledger and recovery pointers before a deliberate change. Mode cancels no work.
4. Add one small marked hook to the actual loaded instruction entrypoint, adapting
   relative paths to its location. Preserve the rest of that file:

   ```markdown
   <!-- producer-pattern:start -->
   Read `.producer/PATTERN.md` and resolve your assignment role first. Delegated
   agents default to worker at every depth. Producers also read PROJECT.md,
   MODELS.md, and STATE.md inside `.producer/`. Workers/reviewers load their
   assignment and applicable project rules; recorders load STATE and its tracked
   references when applicable. Follow the requirements for your resolved role;
   producer-only authority stays with producers.
   <!-- producer-pattern:end -->
   ```

## Verify without polluting the backlog

Verify that the host actually loads the entrypoint and referenced role/context
files. Check canonical state, requested versus actual model controls, and truthful
behavior when delegation/persistence is unavailable. For an existing tracker,
verify its actual mapped workflow and persistence receipts without installing a
new helper or second store. For lean, verify core wiring and current activity/
decision persistence; honestly retain its lack of a complete-ledger promise.

**Only for a new bundled tracked store**, perform the helper checks below. It
needs Python 3.10+ on macOS/Linux for `fcntl` advisory locks. Missing dependencies
or failed checks leave that tracked setup incomplete; report the limitation.
Have the recorder run `validate` on its actual store without modifying it; an
empty store is valid. Separately, have a worker/recorder test the helper lifecycle
in a newly created disposable directory, never by adding dummy actual requests:

1. Copy the selected package helper to `<fixture>/tools/requests.py` and run its
   `init` command. Write a tiny UTF-8 `<fixture>/raw.txt` artificial request. The
   fixture must be separate from the actual project and have its own project ID.
2. Save the literal plan, dispatch, submit, and accept JSON examples from
   [TOOLING.md](references/TOOLING.md) as separate event files in the fixture.
   Its dispatch handle is synthetic fixture input, not an actual execution claim.
3. Substitute the fixture path and returned ID, then run:

   ```sh
   python3 <fixture>/tools/requests.py init
   python3 <fixture>/tools/requests.py create --raw-file <fixture>/raw.txt --title "Fixture only" --event-id fixture-capture-1
   python3 <fixture>/tools/requests.py apply <returned-ID> --event-file <fixture>/plan.json --expect-revision 1
   python3 <fixture>/tools/requests.py apply <returned-ID> --event-file <fixture>/dispatch.json --expect-revision 2
   python3 <fixture>/tools/requests.py apply <returned-ID> --event-file <fixture>/submit.json --expect-revision 3
   python3 <fixture>/tools/requests.py apply <returned-ID> --event-file <fixture>/accept.json --expect-revision 4
   python3 <fixture>/tools/requests.py show <returned-ID>
   python3 <fixture>/tools/requests.py validate
   ```

4. Confirm done under archive/<REQ-ID>/request.md, the linked immutable source
   preserves exact raw text, expected history/revisions, and successful validation. Remove only the disposable fixture afterward. No external test suite
   or maintainer document is required for this check.

Obtain a recorder setup receipt with paths and checks. Report installation
separately from author approval or a successful fresh-session behavioral trial.
Payload links are relative; fill PROJECT locally. Files do not start workers.

## Repeat, upgrade, remove

On rerun inspect existing payload, config, and hook. Reuse one hook; preserve local
PROJECT context and contract adaptations. Compare with the selected incoming
manifest; back up conflicting files to unique dated paths before a worker merges.
Never overwrite local edits blindly or migrate a tracker as an upgrade side effect.
Record source/version, backups, and changes in PROJECT.md.

For removal, have the recorder identify unfinished requests, actual handles,
pending evaluation, and decisions. Reconcile execution and retain records at an
agreed reachable location. Remove the marked hook and unused contract files only;
preserve unfinished state and recovery pointers. Removing files stops no agents.
