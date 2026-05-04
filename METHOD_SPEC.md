# Verified AI Operations — Method Specification

## 1. Purpose

Verified AI Operations is a method for using AI in business, evidence, agentic, and robotic contexts without treating raw model output as operational truth.

It provides a verification and provenance layer over AI systems so that every output or action can be labelled, challenged, audited, and traced.

## 2. Problem

General-purpose AI assistants can be useful, but they create risk when they:

- answer before verifying;
- claim completion without evidence;
- hide tool, memory, retrieval, or file context;
- generate polished unsupported claims;
- shift testing and repair burden onto users;
- rely on unlabelled synthetic or recycled data;
- provide exports that omit operational records.

## 3. Core method

```text
User request
  -> intent router
  -> capability layer
  -> draft answer / candidate action
  -> RA Refinery
  -> evidence graph comparison
  -> verification status
  -> audit event
  -> final answer
```

The AI may still be powerful and convenient, but final output is not trusted until verified or labelled.

## 4. Capability layer

The capability layer may include:

- hosted LLMs;
- local LLMs;
- web search;
- WordPress/API retrieval;
- local file search;
- evidence graph search;
- code execution;
- document analysis;
- voice input;
- file attachments;
- future robotics/sensor systems.

Capability tools generate candidate material. They do not decide final truth status.

## 5. RA Refinery

RA Refinery performs:

- claim extraction;
- evidence lookup;
- node matching;
- provenance scoring;
- contradiction detection;
- ownership checks;
- completion-proof checks;
- high-impact claim thresholding;
- unsupported-claim labelling;
- audit record creation.

## 6. Output statuses

Every final output receives one of these statuses:

```text
VERIFIED
PARTIALLY VERIFIED
NOT VERIFIED
INSUFFICIENT EVIDENCE
ACTION NOT COMPLETED
REFUSED FOR SAFETY
```

## 7. Completion rule

The system must not say or imply the following unless the audit record proves the action occurred:

```text
done
fixed
completed
created
sealed
wired
located
tested
backfilled
fully operational
```

If proof is absent, the system must say the action is not verified or not completed.

## 8. Evidence graph node

Each evidence node should include:

```json
{
  "node_id": "NODE-000001",
  "claim": "The task was completed",
  "source": "file/chat/tool/sensor/business-record",
  "ownership_status": "owned|approved|public_candidate|blocked",
  "verification_status": "verified|partial|not_verified",
  "created_at": "ISO-8601",
  "sha256": "",
  "contradictions": [],
  "confidence": 0.0
}
```

## 9. Audit event

Each output writes an audit event containing:

- request hash;
- tools used;
- evidence nodes used;
- unsupported claims;
- contradiction result;
- ownership result;
- final status;
- timestamp;
- prior audit hash;
- current audit hash.

## 10. Distinguishing feature

The method preserves a normal chatbot experience while adding a visible verification status and an inspectable provenance/audit layer underneath.
