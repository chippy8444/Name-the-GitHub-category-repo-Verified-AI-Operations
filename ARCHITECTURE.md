# Verified AI Operations Architecture

## System overview

```text
Resolution AI / Sovereign Engine
  ├── UI layer
  │   ├── normal chat interface
  │   ├── file attachment
  │   ├── microphone input
  │   ├── verification badge
  │   └── trace drawer
  ├── intent router
  ├── capability layer
  │   ├── hosted LLMs
  │   ├── local LLMs
  │   ├── local files
  │   ├── web candidates
  │   ├── WordPress/API sources
  │   └── code/document tools
  ├── evidence graph
  ├── ownership guard
  ├── RA Refinery
  ├── audit log
  └── export/report layer
```

## Operating modes

| Mode | External calls | Purpose |
|---|---:|---|
| Airgap | No | highest privacy, local graph/files only |
| Hybrid Verified | Minimal | balanced capability and privacy |
| Full Capability | Yes | maximum capability, still verified |
| Evidence Lockdown | No | legal/evidence preservation mode |

## Data flow

```text
Input
 -> classify request
 -> gather candidates
 -> store tool trace
 -> draft answer
 -> extract claims
 -> match claims to evidence
 -> detect contradictions
 -> apply proof thresholds
 -> label output
 -> write audit hash
 -> show answer
```

## Hosted-tool rule

Hosted AI output is draft material only. It can help compose, reason, or summarize, but final truth status must be assigned by RA Refinery.

## Local storage

Recommended default storage target:

```text
D:\SovereignRA\data\private
D:\SovereignRA\logs
```

If D: is unavailable, the system must display the fallback local storage folder clearly.

## Trace visibility

A user should be able to inspect:

- what was searched;
- what files were used;
- what tools were called;
- what evidence nodes supported the answer;
- what could not be verified;
- the audit ID/hash.

## Main design target

The product should feel like a normal high-quality AI assistant. The only visible difference should be that every answer includes a verification status and optional trace access.
