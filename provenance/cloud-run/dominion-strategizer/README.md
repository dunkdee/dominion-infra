# Dominion Strategizer Cloud Run Manifest

This directory records the observed deployment identity for provenance repair #145.

- Project: `dominion-ascendant`
- Region: `us-central1`
- Service: `dominion-strategizer`
- Ready revision: `dominion-strategizer-00003-8t9`
- Image digest: `sha256:ecd699e505cb37ec909ca5ce067469aeb0a468c788923cf0289efeafe939a620`
- Runtime service account: `288811801522-compute@developer.gserviceaccount.com`
- Ingress: `all`
- Health endpoint: `GET /health` → HTTP `200` on 2026-08-11

Application source is versioned separately in `dunkdee/dominion-ops/apps/strategizer`.

## Hold

`service.yaml` is a reviewable observed-state manifest. Do not apply it automatically. Issue #145 does not authorize deployment, traffic changes, service restart, IAM changes, secret access, or environment mutation.
