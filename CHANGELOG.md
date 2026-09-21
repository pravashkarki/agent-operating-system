# Changelog

## v1.0.0 - 2026-09-21

- `LICENSE.md` replaced by `LICENSE` carrying the canonical CC BY 4.0 text. The previous file was a short paraphrase, which GitHub could not detect, so the repo showed no license at all. The plain-language terms now live in the README.
- Repository homepage set to the essay that explains the model.
- `AGENTS.md` is now the canonical file a repository carries; `CLAUDE.md` points at it. `AGENTS_TEMPLATE.md` and `AGENTS.example.md` replace the `AGENT_PROJECT` equivalents, and the session entry rule reads `AGENTS.md` first. `AGENT_PROJECT.md` stays available for a project that spans several repositories, and existing ones keep working. This supersedes the 2026-04-12 rule that treated `AGENTS.md` as a Codex compatibility adapter only; that rule deferred the change until a real adoption tested it, and the adoption came back the other way.

## 2026-08-30

- First public edition, sanitised from the private system in use since April 2026.
- Added after external peer review: defined lighter mode; agent-to-agent conflict rules; cost and token budget; untrusted input and data handling; outages and degraded mode; owner absence; rollback protocol; onboarding and retiring rules; authorisation boundary inside and outside the approved plan; deferral as the owner's decision; commit-as-you-go with `sss` as the check.
- README rewritten for a two-minute read; `examples/` with a filled project file and a two-agent scenario.
