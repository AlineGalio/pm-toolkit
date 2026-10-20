# US-001: Move application secrets to a secrets vault

**Epic / Debt item:** EX-01 (Credentials committed in repository)
**Priority:** Act now (score 25)
**Estimate:** 16 h

## Story
As a **security officer**, I want **all database and API secrets stored in a managed vault instead of the repository**, so that **a repository leak cannot expose production access**.

## Context
The Broker Portal API keeps database and partner API credentials in config files under version control. Anyone with read access to the repository, or to its history, can reach production data. This is the highest-scored item in the assessment (Risk 5 × Impact 5).

## Acceptance criteria
1. **Given** the secrets inventory, **when** the team reviews the repository, **then** every exposed credential is listed with its owner and system.
2. **Given** an exposed credential, **when** the story is deployed, **then** it has been rotated and the old value no longer authenticates.
3. **Given** the API starts in any environment, **when** it needs a secret, **then** it reads it from the vault and no secret exists in config files, environment files or build logs.
4. **Given** a commit that contains a secret pattern, **when** the pipeline runs, **then** the build fails and reports the file and line.
5. **Given** the repository history, **when** the cleanup is finished, **then** a scan of all branches and tags finds no valid credential.
6. **Given** the vault is unavailable at startup, **when** the API starts, **then** it fails fast with a clear error and does not fall back to local values.

## Out of scope
- Rotating end-user passwords
- Secrets of other applications

## Dependencies and risks
- Vault access for the three environments: Platform team **[to be confirmed]**
- Rotation requires a maintenance window with partner teams
- Rewriting history needs all developers to re-clone

## Notes
Rotate first, purge history second. Purging alone does not make a leaked secret safe.
