# Public repository rules

## Rule 0: synchronize before work

Before starting work, inspect `git status --porcelain` and require a clean working
tree. If there are local changes, stop and report them without altering them.
Run `git pull --ff-only` on the intended branch with its verified upstream before
editing files. Stop and report any conflicts, divergence, missing upstream,
authentication error, or network failure. Never use autostash, reset, a forced
update, or an automatic merge to bypass this rule.

The only exception is an initial empty repository: explicitly verify the exact
remote repository identity and confirm with a successful `git ls-remote` that the
remote has no refs. Only then create and publish an initial commit. After that,
normal clean-status and `git pull --ff-only` synchronization applies.

## Public scope

This repository contains only generic, public, reusable plugins, skills, and
adapters. Keep private customization in a private repository. Keep domain and
business logic in the owning cores; expose only generic integration interfaces
here. Preserve unrelated existing content and user changes.

## Prohibited content

Never add or publish secrets, access tokens, passwords, credentials, private keys,
cookies, personal data, private or internal customer configuration, private
hostnames, host-specific paths, closed business workflows or scenarios, runtime
dumps, logs containing private data, or production exports. This applies to source,
documentation, examples, tests, fixtures, filenames, commit messages, Git history,
archives, generated files, and other published artifacts.

Use synthetic examples and obvious placeholders only. Do not copy private
configuration and merely mask selected values. Do not copy an old repository's
`.git` directory, import its history, or add old plugins without a separate,
explicitly authorized public-content review.

## Before every publication

Scan and review the complete history being added, not only the current diff or
working tree. Inspect every added commit and all associated artifacts, including
archives and generated output, for secrets and private information. Use available
secret-scanning tools plus contextual review for personal data, internal settings,
private hostnames, machine-specific paths, and business-specific material. Confirm
that all examples are synthetic and that only intended public content is included.
If a required scan cannot complete, stop publication and report the blocker.

## Incident handling

If prohibited material is found or suspected, stop publication immediately and
report the affected location and category without printing sensitive values.
Do not silently rewrite history, delete evidence, revoke credentials, or change
repository visibility. Obtain explicit owner instructions for incident remediation.
