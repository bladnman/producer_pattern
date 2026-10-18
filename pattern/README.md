# Install the Producer Pattern

**First candidate · October 16, 2026.** This subtree is a self-contained package
for agents installing the method in a target project. It is not a proven adoption.

Give one project a producer who discusses, decides, coordinates workers, evaluates
evidence, requests rework, and accepts the integrated outcome. The producer is a
non-worker: workers execute; Small clerks map broad material; a Small recorder
handles routine state reading/writing. Selective critical reading and ordinary
discussion stay with the producer. No department tree is required.

Tracked is the default for new installations; lean is an explicit optional choice.
Keep an existing tracker canonical. New bundled stores use request folders with
shared immutable user sources and typed relationship/ownership records. Files
preserve continuity, not agent liveness
or an automatic wakeup. No service, scheduler, or new chat is installed.

Periodic supervision reports use **📋 SitRep** so they are easy to scan or skip.
This labels the report block; the checked producer's `🎬` identity, `❓` questions,
and `🖐️` user-only actions keep their meanings. See [PATTERN.md](PATTERN.md) for
the sparse marker rules and supervision requirements.

## Adopt in a target project

Ask the agent working in that project:

```text
Read this package's README.md and follow its INSTALL.md to install the candidate
Producer Pattern in the target project. Preserve existing instructions, local
adaptations, unfinished work, and the canonical tracker. Copy only the selected
manifest payload, fill PROJECT.md from real context, and verify supported host
capabilities. Do not publish, migrate requests, or copy the whole source repository.
```

Use this [package entrypoint](https://github.com/bladnman/producer_pattern/blob/main/pattern/README.md)
when pointing an agent at the published repository. A staging clone is optional
transport, not a request to adopt everything in the checkout.

Follow [INSTALL.md](INSTALL.md). [manifest.json](manifest.json) is the authoritative
copy list: base files are always payload; tracked files are added only for a new
bundled tracked store. Preserve their relative paths under the target `.producer/`.
README, INSTALL, and manifest guide the operation; they are not installed payload.
No maintainer rationale, user-source history, tests, private archive, repository
metadata, or authoring instructions belong in the target installation.

Read [PATTERN.md](PATTERN.md), [MODELS.md](MODELS.md), [STATE.md](STATE.md), and the
fillable [PROJECT.md](PROJECT.md) as needed for setup. The package depends on no
files outside this subtree. Reading alone is not adoption; an adoption request
authorizes the reversible setup. Host restrictions and existing authority remain.

## Update an existing installation

Ask the project agent to follow its installed [update protocol](references/UPDATES.md),
or this package's [INSTALL.md](INSTALL.md) when the older installation has none.
Use published GitHub `main` resolved to an exact reviewed commit, preserve local
adaptations and private state, and verify before recording the new revision.
An update request is distinct from reading the repository; startup does not silently
update an installation.
