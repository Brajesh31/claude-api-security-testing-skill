# claude-api-security-testing-skill

A Claude Code skill for assessing the security of REST and GraphQL APIs through authorized testing and defensive validation.

## Overview

This skill provides a structured workflow for identifying API security weaknesses. It focuses on authentication, authorization, input validation, rate limiting, data exposure, and API-specific attack surfaces.

Use it only against systems that the user owns or is explicitly authorized to assess.

## Main Assessment Areas

- API endpoint discovery and inventory.
- Authentication and session validation.
- Object-level and function-level authorization.
- Input validation and schema enforcement.
- Rate limiting and abuse prevention.
- Sensitive data exposure.
- GraphQL schema and resolver access controls.
- Error handling and information leakage.
- Security configuration and transport protections.

## When to Use It

Use the skill when testing REST or GraphQL APIs, validating authentication and authorization, reviewing rate limits, or preparing an API security assessment.

## Installation

```bash
git clone https://github.com/Brajesh31/claude-api-security-testing-skill.git ~/.claude/skills/api-security-testing
```

## Usage

Invoke the skill for an authorized API security review:

```text
/api-security-testing
```

Provide the API base URL or local project, scope, authorization details, test environment, allowed methods, and prohibited actions.

## Assessment Workflow

1. Confirm authorization and scope.
2. Inventory routes, methods, and API schemas.
3. Identify authentication mechanisms.
4. Review object and function authorization.
5. Test input validation using safe, bounded cases.
6. Review rate limits and resource controls.
7. Check data exposure and error behavior.
8. Assess GraphQL access controls where applicable.
9. Record reproducible evidence.
10. Prioritize findings and recommend remediation.
11. Re-test fixes within the approved scope.

## Reporting Format

| Field | Description |
|---|---|
| Finding | Clear vulnerability or weakness |
| Endpoint | Affected route or operation |
| Preconditions | Required account or role |
| Evidence | Sanitized, reproducible proof |
| Impact | Realistic consequence |
| Severity | Risk-based priority |
| Remediation | Specific fix |
| Retest | Verification result |

## Security Checklist

- Authentication is required where appropriate.
- Authorization is checked for each protected resource.
- User-controlled identifiers cannot bypass ownership checks.
- Inputs are validated against expected schemas.
- Sensitive fields are not returned unnecessarily.
- Rate limits protect expensive operations.
- Errors do not reveal secrets or internal details.
- GraphQL resolvers enforce access controls.
- Logs avoid sensitive request data.
- Tests cover both permitted and denied access.

## Repository Contents

- `SKILL.md`: Main API security testing workflow.
- `README.md`: Scope, assessment phases, and reporting guidance.

## Safety Boundaries

- Do not test systems without explicit authorization.
- Avoid destructive operations and service disruption.
- Do not access unrelated user data.
- Stop if testing reveals unexpected sensitive information.
- Keep evidence sanitized.
- Respect rate limits and agreed testing windows.

## Practical Principle

A successful request does not prove an API is secure. Test authorization boundaries and failure cases, and report only findings supported by evidence.
