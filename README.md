# Assisted business document type suggestions (ES/PT/EN)

Public integration examples for Software Sushi's assisted 1.0 model. It offers
two possible types for a person reviewing already extracted English, Spanish or
Portuguese business text. A person must choose or reject the suggestions.

**Marketplace publication is pending.** The exact image completed private AWS
technical qualification; owner review approved the scope, sources/limitations
and USD0.50 per instance-hour with a fourteen-day software trial. AWS infrastructure
is separate, including during trial. Check [current release status](https://ss-document-media-637423513289-us-east-1.s3.us-east-1.amazonaws.com/document-type-classifier/1.0.0/status.html)
before looking for a subscription. This repository is not a live offer.

## Try the notebook

[Open the complete Boto3 notebook](notebooks/assisted-document-suggestions.ipynb).
Default Run All is offline and makes no AWS requests. It contains its own fictional
sample text. Once subscribed, copy the regional model-package ARN from Marketplace,
provide your existing SageMaker execution role, review costs/access/cleanup, then
explicitly enable the real-time or batch example. Use a current boto3 release.

Real-time creates one ml.c5.xlarge endpoint and deletes its own endpoint, config
and model in finally. Retain the printed name: kernel termination does not stop
billing. Batch requires your existing authorized us-east-1 S3 bucket, writes a
unique example prefix, runs SingleRecord at concurrency one, and cleans its model
after compute stops. Its small S3 input/output objects are retained for inspection.
Neither path creates a bucket or IAM role. No CI/CD is used.

For the seller's own certified source, the preflight verifies its actual Catalog
association with the Limited/Public product and Released offer. This owner-only
path is a seller rehearsal, not an independent buyer subscription or checkout
test. Ordinary subscribed packages use their Marketplace identity path.

## Inputs and actual outputs

- [Single request](examples/request.json) and [actual AWS response](examples/response.json).
- [Three-language JSON Lines input](examples/batch.jsonl) and [actual batch output](examples/batch-output.jsonl).

Outputs were recorded from the exact certified image, not handwritten predictions.
All texts are fictional/model-authored. The examples are exposed diagnostics,
not independent acceptance or customer accuracy measurements.

## Scope and bounds

Seven categories: purchase order, delivery note, bank statement, utility bill,
insurance policy, invoice and other business correspondence. The caller establishes
that the source is one supported document before requesting suggestions. Unrelated
or combined text still receives suggestions. No OCR, unknown/mixed detection,
authenticity check, field extraction, confidence probability or automatic routing.

1–32 records per envelope, 256 KiB body, 16,000 Unicode code points per text and
256 complete encoder tokens including prefix/special tokens. Reject overflow
without truncation. Rank is not confidence. IDs/filenames are metadata, not features.
Always keep manual review and selection/rejection in downstream workflows.

## Evidence and sources

[Model card](https://ss-document-media-637423513289-us-east-1.s3.us-east-1.amazonaws.com/document-type-classifier/1.0.0/model-card.html) ·
[Guide](https://ss-document-media-637423513289-us-east-1.s3.us-east-1.amazonaws.com/document-type-classifier/1.0.0/usage.html) ·
[Sources/licenses](https://ss-document-media-637423513289-us-east-1.s3.us-east-1.amazonaws.com/document-type-classifier/1.0.0/sources.html).

Validation uses generated data only; there are zero native documents or independent
human acceptance labels. Real customer-document accuracy is unmeasured. The model
card retains author/AI-reviewer disagreements and sensitivity. Validate with your
own authorized representative examples before operational use.

The frozen intfloat/multilingual-e5-small encoder is MIT-licensed; original Software
Sushi serving code/head are Apache-2.0. This public repository contains only original
SDK examples and fictional texts, not encoder weights or private development data.

[Walkthrough](https://youtu.be/nri46eID0-4) · [Short](https://youtube.com/shorts/aOFRDhthm2g).
These illustrative-UI review videos make actual model calls and require manual choice.
AI narration is disclosed. No human listening review is claimed.

Support: info@softwaresushi.com. Include version, instance type and request ID;
do not send document contents, private data or credentials. No support-time SLA.
