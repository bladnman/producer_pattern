# Producer Pattern

**First candidate · October 16, 2026.** One project producer stays in conversation,
coordinates workers, evaluates evidence, and accepts the whole outcome. Workers
execute; a small recorder preserves state. Tracked is default; lean is optional.

**New here? [Start with the website](https://producer.metal-sole.com/)** for the
overview and copyable requests to install, check, or update it through your
project's existing agent. Website source and hosting notes live in [site/](site/).

**For an agent:** [read the website's guide](https://producer.metal-sole.com/install.md)
to continue to the canonical GitHub installation or update protocol.

**Here to install? Start with [pattern/README.md](pattern/README.md).** That subtree
stands alone. Install only its manifest-listed payload into the target project's
`.producer/`; the rest of this repository is not part of the installation.
A temporary clone may transport files, but copying the checkout is not adoption.

**Here to develop the pattern? Read [development/RATIONALE.md](development/RATIONALE.md)**
for the reasons, tradeoffs, and open decisions, then follow this
repository's [authoring guidance](AGENTS.md). Maintainer material is not required
for installation. Local adoption is separate: when configured, the optional local
startup hook activates an installation. A source checkout alone does not install
the pattern or confer producer authority.

Candidate authorship, target installation, fresh-session verification, and public
publication are separate steps. The source repository is
[bladnman/producer_pattern](https://github.com/bladnman/producer_pattern);
the agent installation entrypoint is [pattern/README.md](pattern/README.md).

For an existing installation, use the [update protocol](pattern/references/UPDATES.md).
Published GitHub `main` is the upstream source of truth; agents pin each installation
or explicit update to an exact reviewed commit rather than silently updating at startup.

## Optional global skill

On request, copy just [skill/producer-pattern/SKILL.md](skill/producer-pattern/SKILL.md)
to the host's per-user skill directory. For Codex, use
`$CODEX_HOME/skills/producer-pattern/SKILL.md` when `CODEX_HOME` is set, otherwise
`~/.codex/skills/producer-pattern/SKILL.md`; for other hosts, use their user-level
skill directory. Preserve an existing skill before replacement.
Do not install a project-local skill by default. This tiny optional pointer routes
lifecycle requests to the current canonical guide; installing it does not install
the pattern in any project. On a request to remove the global skill, remove only
its `producer-pattern/SKILL.md` and its directory if empty, preserving other skills
and all project installations.
