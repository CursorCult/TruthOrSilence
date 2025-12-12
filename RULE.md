---
description: "Delete false internal prose; truth or silence"
alwaysApply: true
---

# TruthOrSilence Rule

TruthOrSilence applies to internal developer prose only: comments, docstrings, internal READMEs, wikis, and design notes. Public/user‑facing documentation correctness is assumed baseline and is not the focus of this rule.

A codebase under TruthOrSilence must contain no false internal prose.

## Requirements

- Any internal prose that is false, outdated, unverifiable against the current codebase, or contradicted by code/tests must be deleted.
- Deletion is the only mandatory action under this rule. There is no requirement to replace a lie with new prose.
- TruthOrSilence sets no standard for how much to comment or what style to use; it only governs truthfulness.

## Commit protocol

- Codebases using TruthOrSilence must follow this protocol for removing a lie:
  - The lie removal is isolated to its own commit containing only that deletion.
  - The full word `TruthOrSilence` must appear in the commit subject (in addition to satisfying any other commit‑message rules the codebase uses).
  - The commit body must explain why the prose is known to be false (what current code/tests contradict it).
- After the lie‑deletion commit, adding replacement truth is optional and treated as a normal documentation/commenting change, subject to whatever documentation rules the codebase uses. It must be in a separate commit.

## Relationship

- Pinocchio is preventive (minimizes future lie risk): https://github.com/CursorCult/Pinocchio.git
- TruthOrSilence is absolute in the present (no lies exist now).
