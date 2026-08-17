# Security and privacy boundary

This public case-study repository intentionally excludes production source code, credentials, private configuration, and raw personal trading data.

The live system uses the following security boundaries:

- Read-only market-data collection
- Signed ingestion requests
- Timestamp validation and replay protection
- Payload validation and size limits
- Separate authorization for administrative model actions
- No order-placement capability
- No broker-account password stored by the dashboard

Operational secrets are managed outside the public portfolio repository. Any future open-source release would require a separate security review, removal of environment-specific details, and documented credential rotation.
