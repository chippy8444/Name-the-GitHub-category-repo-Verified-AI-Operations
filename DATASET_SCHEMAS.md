# Verified AI Operations Dataset Schemas

The category requires datasets that distinguish verified reality from synthetic noise, false completion, and unsupported AI output.

## 1. RA-HVI — Human Verified Interaction Dataset

Captures user requests, AI answers, verification results, corrections, and audit outcomes.

```json
{
  "record_id": "RA-HVI-000001",
  "user_request": "",
  "ai_answer": "",
  "verification_status": "not_verified",
  "supporting_nodes": [],
  "contradicting_nodes": [],
  "human_review": "",
  "corrected_answer": "",
  "audit_hash": ""
}
```

## 2. RA-VRD — Verified Reality Dataset

Captures real-world records with provenance.

```json
{
  "record_id": "RA-VRD-000001",
  "observation": "",
  "source_type": "sensor|document|human|business_record",
  "timestamp": "",
  "ownership_status": "",
  "consent_status": "",
  "chain_of_custody": [],
  "sha256": ""
}
```

## 3. RA-SCD — Synthetic Contamination Dataset

Labels AI-generated or suspected synthetic data.

```json
{
  "record_id": "RA-SCD-000001",
  "content": "",
  "synthetic_status": "synthetic_suspected",
  "reason": "",
  "source_trace": [],
  "risk": "training_contamination"
}
```

## 4. RA-CPD — Completion Proof Dataset

Tracks false and verified completion.

```json
{
  "record_id": "RA-CPD-000001",
  "task": "",
  "ai_claimed_status": "done",
  "actual_status": "not_completed",
  "evidence_for_completion": [],
  "evidence_against_completion": [],
  "rework_cost": "",
  "verification_status": "not_verified"
}
```

## 5. RA-RAV — Robot Action Verification Dataset

```json
{
  "record_id": "RA-RAV-000001",
  "instruction": "",
  "task_state": "",
  "authority": "",
  "sensor_evidence": [],
  "safety_envelope": "",
  "action_taken": "",
  "abort_conditions": [],
  "completion_proof": [],
  "safe_to_act": false,
  "audit_hash": ""
}
```

## 6. Core labels

```text
human_original
human_verified
sensor_verified
business_record_verified
synthetic
synthetic_suspected
mixed_origin
export_sanitised
completion_false
completion_verified
tool_loop
billing_harm
privacy_gap
unsafe_to_act
safe_to_answer_only
human_review_required
```

## 7. Dataset principle

Ordinary datasets say: here is content.

Verified AI Operations datasets say: here is content, its origin, its proof, its contradiction state, its ownership, and whether it is safe to act on.
