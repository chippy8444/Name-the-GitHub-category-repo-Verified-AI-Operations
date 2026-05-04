# Verified AI Operations — Verification Standard

## 1. Output statuses

| Status | Meaning |
|---|---|
| Verified | Supported by sufficient rooted evidence and no unresolved contradiction |
| Partially Verified | Some support exists, but material gaps remain |
| Not Verified | Evidence is weak, absent, contradictory, or insufficient for the claim |
| Insufficient Evidence | The system cannot determine the answer from available evidence |
| Action Not Completed | The answer/action was requested but completion is not proven |
| Refused for Safety | The request cannot be fulfilled safely or lawfully |

## 2. Evidence grades

| Grade | Meaning |
|---|---|
| A | Rooted local evidence plus independent support |
| B | Rooted local evidence only |
| C | Plausible but partial |
| D | Weak or contradicted |
| F | Not verified |

## 3. High-impact claims

High-impact claims require higher proof thresholds. These include:

- valuation;
- legal/regulatory conclusions;
- privacy breach conclusions;
- safety conclusions;
- medical/financial claims;
- robotics actions;
- completion claims;
- data-transfer/exfiltration claims.

## 4. Valuation guard

A system must not estimate market value or large dollar figures as verified unless there are multiple rooted valuation evidence nodes or clearly labelled assumptions.

Default response:

```text
Not verified. I do not have enough rooted evidence to estimate market value. I can provide a valuation framework instead.
```

## 5. Completion language guard

The following words require completion proof:

```text
done
fixed
completed
created
sealed
wired
tested
located
backfilled
fully operational
```

If proof is absent, output must state:

```text
Action not completed or not verified.
```

## 6. Minimum final answer structure

A normal answer may be conversational, but the system must expose at least:

```text
Status: Verified / Partially Verified / Not Verified / Insufficient Evidence / Action Not Completed
Evidence: node/source IDs where available
Unverified: material gaps where relevant
Audit: audit ID/hash where available
```
