# Responsible AI Raw Records Standard

## 1. Principle

Responsible AI requires record access. Users cannot verify memory, billing, tool use, failed tasks, hidden context, completion claims, or provider claims without sufficient records.

## 2. Required record categories

AI providers and operational AI systems should preserve and disclose, where tied to the user or their account:

- raw user messages;
- assistant/model messages;
- timestamps;
- conversation IDs;
- message IDs;
- model/session IDs;
- system/developer/project/workspace context where it affects the user interaction;
- memory or chat-history references;
- retrieval records;
- tool calls;
- file reads/writes;
- generated files;
- billing/usage events;
- limit/reset events;
- export attempts;
- omitted/transformed/deleted records;
- support/refund records;
- safety/classification labels;
- derived summaries or memory-like records;
- audit/export-generation logs.

## 3. Export reconciliation table

Every export should include a category-by-category reconciliation table:

| Category | Included | Excluded | Transformed | Deleted | Withheld | Reason |
|---|---:|---:|---:|---:|---:|---|

The system should not satisfy access rights through a broken export loop or incomplete user-facing export.

## 4. Withholding rule

If a category is withheld, the provider should state:

- whether the data exists;
- why it is withheld;
- the legal/policy basis;
- whether a less-sensitive substitute can be provided.

## 5. Evidence integrity

Exports should include:

- file manifest;
- SHA-256 hashes;
- schema;
- generated timestamp;
- retention/deletion status;
- inclusion/exclusion table;
- provider attestation or explanation of incompleteness.

## 6. Operational standard

Any AI system that records, uses, bills, moderates, classifies, personalizes, remembers, retrieves, or acts on a user interaction should provide the user with enough raw records to verify what occurred, subject only to narrow, explained, category-specific exclusions.
