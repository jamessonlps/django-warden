# Portable skill extraction

Source: [allia-admin PR #171](https://github.com/maiquelleonel/allia-admin/pull/171),
published commit `989e56c127c28461ceeaf7318db028ef7e4329ec` only. Unpublished changes
in the consuming application are outside this contribution.

## Preserved guidance

The six entrypoints retain their distinct discovery scopes. Their references
preserve the operational distinctions that prevent plausible but wrong changes:

- Backend: model ownership, reciprocal identity writes, constraints, normalization,
  field precedence/length, query growth, update_fields limits, delete signals,
  signal recursion, actual transaction boundaries and non-durable on_commit delivery.
- Templates: version-gated Django partials, isolated include context and CSRF,
  same-name Admin inheritance, query evaluation, source CSS and asset execution order.
- HTMX: exact request-header comparison, empty POST binding, full/fragment permission
  parity, response shapes, non-3xx redirect headers, cache/history separation,
  public DOM targets and required non-JavaScript fallback.
- Alpine: component ownership, sibling events, repeated swaps, lifecycle cleanup,
  actual CSP build, safe JSON output, detached-opener focus and browser verification.
- Security: data and related-choice scope, CSRF enforcement, active HTML attributes,
  response nonce lifetime, upload limits/quarantine and authorized serving.
- Testing: meaningful negative cases, unchanged rejected writes, commit/rollback,
  representative query counts, browser versus server evidence, independent evaluation
  with hidden oracles, model identity and honest limitations.

## File disposition

Paths below are relative to the original `.agents/skills/`; the portable destination
is `django_warden/skills/` with the same skill name unless explicitly renamed.

- `django-backend/SKILL.md`: replace Allia routing with the consuming repository's
  active instructions and local companion. Keep `architecture.md` and
  `data-integrity.md` unchanged. In `evolution.md`, replace the example identity name.
  `references/allia.md` stays consumer-side: app-specific ownership, paths,
  queue/LLM conventions, historical runtime observations and local governance.
- `django-templates/SKILL.md`: generalize stack claims, app names and test invocation.
  `references/shared-ui.md`: neutral app paths and project-policy attribution.
  `references/admin-ui.md`: retain the two-block inheritance example as a generic
  case and generalize prefix-middleware advice. `references/tailwind.md`: generalize
  the ignored asset root and dedicated build command. License notice is unchanged.
- `django-htmx/SKILL.md`: replace the dated Allia HTMX version observation with
  per-page version discovery. All four references are unchanged.
- `alpinejs-django/SKILL.md`: unchanged. `references/htmx-csp.md`: substitute neutral
  app paths while preserving every lifecycle, event, CSP and focus rule.
  License notice is unchanged.
- `django-web-security/SKILL.md`: generalize the final local-governance paragraph.
  `references/web-boundaries.md`: unchanged.
- `django-testing/SKILL.md`: generalize the test runner, coverage and complexity
  policy; local projects retain their stricter requirements. Rename
  `references/allia-integration.md` to `references/project-integration.md`, retaining
  its five discriminating cases and evidence limits with neutral names.
  `references/django-runner.md`: keep commit/rollback patterns; replace the local
  supports_defer override with an immediate-execution example and explicitly
  distinguish real scheduling. The original task fixture stays consumer-side.
  `references/browser-cases.md`: retain independent evaluation methodology while
  making model selection and revision budget task-specific.

The original `.agents/skills/django-warden/SKILL.md` is a generated copy of this
package's core guide, so it is not imported as a second source. Narrow corrections
to that guide and its packaged template align Forms, update_fields, signals,
uploads and workflow ownership with the source-backed companion guidance.

## Consumer migration

Retain Allia's `allia.md` and `allia-integration.md` in a separately named local
companion before retiring its maintained catalog copies. Also retain its runner
and coverage/complexity policy, deferred-task fixture, UI/source observations and
earlier model-evaluation parameters there. Link that companion from the active
repository instructions and expose it to the project's assistants.

Claude settings/permissions, Claude skill links, `.codex/skills`, and the local
AgentSpec README belong to the consuming project. They are not imported upstream.
The conflict policy deliberately preserves existing custom skills until their owner
reviews this separation and moves the old directory to a backup. Package updates
can then manage the portable copies without becoming the owner of local policy.

The contribution does not select a release number or change a consumer's lockfile.
After the maintainer releases it, update the consuming dependency and bootstrap.
