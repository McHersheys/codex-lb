# Reuse bridge sessions for inline images

## Why

Any image in retained history currently disables reusable HTTP bridge sessions. Switching the standalone transport to WebSocket in #2363 did not restore connection reuse.

## What Changes

Allow otherwise eligible inline images within the frame budget through the existing bridge. Preserve external-URL, oversized-payload and image-generation exclusions. Cover physical connection reuse, pre-acknowledgement errors and cancellation cleanup.

## Capabilities

### Modified Capabilities

- `responses-api-compat`: inline-image bridge eligibility and lifecycle safety.

## Impact

One routing condition; no new settings, dependencies, schema or wire format. Provider cache hits are not guaranteed.
