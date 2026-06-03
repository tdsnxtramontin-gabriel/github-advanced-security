# GitHub Secret Protection
GitHub Secret Protection is designed to detect and prevent secrets from being exposed throughout the development lifecycle. In application security, a secret is any sensitive credential or confidential value that grants access to systems, services, or data. Examples include API keys, tokens, passwords, and cloud credentials. Secret Protection helps organizations reduce the risk of accidental exposure before secrets are committed, pushed, or left undiscovered in repository history.

## What is Secret Scanning?
Secret scanning is a GitHub Advanced Security feature that scans repositories for known types of secrets. It prevents the fraudulent use of secrets that were committed accidentally. Secret scanning automatically scans your entire Git history on all branches present in your GitHub repository for any secrets. When a secret with a known pattern is committed into a private or public repository in your project, secret scanning sends a notification to all repository administrators about the commit that contains the secret. Repository administrators can then view the list of all detected secrets in the repository's Security tab. GitHub also notifies the service provider who issued the secret if they're partnered with GitHub.

Secret scanning scan the following:
- Descriptions and comments in issues.
- Titles, descriptions, and comments, in open and closed historical issues.
- Titles, descriptions, and comments in pull requests.
- Tittle, descriptions, and comments in GitHub Discussions.

**Secret Scanning Availability:**
- Public Repositories: Enabled by default and cannot be turned off. Alerts are available for free.
- Private Repositories: Requires manual enabling and a GitHub Advanced Security license for secret scanning.

**Enabling Secret Scanning:**
- Repository Level: Navigate to Settings > Code security and analysis, enable GitHub Advanced Security, Secret Scanning, and Push Protection.
- Organization Level: Enable GitHub Advanced Security and Secret Scanning for all private repositories, with options for automatic enabling on new repositories.

## What is Push Protection?
Push Protection helps stop secrets before they are committed to the codebase. It detects exposed secrets during the push process and alerts developers immediately, allowing them to remove or remediate the issue before merge.

- Scans for identifiable secrets before they are pushed, prompting contributors to remove or bypass detected secrets.
- Default settings: Enabled by default for public projects to prevent accidental secret leaks.
- User Experience: Provides remediation guidance directly in the IDE or command-line interface.

## What is Custom Patterns?
- Purpose: Organizations can define custom secret scanning patterns for company-specific or internally defined secrets.
- Scope: Supports up to 500 custom patterns per organization or enterprise account, and up to 100 per private repository.
- Scanning: Scans the entire Git history on all branches and alerts administrators.

## What is Validity Check?
GitHub can validate whether a detected secret is still active, helping teams prioritize real exposure and reduce false positives.
- Determine if a token is still active or was ever active, aiding in remediation decisions.
- Use Case: Prioritize remediating active secrets and checking security logs for unauthorized access.
- Helps streamline the process of managing exposed credentials effectively.

## Other Features
**Delegated Bypass**
If a developer believes a push should proceed despite a detected secret, a bypass request can be submitted for review. Delegated bypass enables designated reviewers to approve or reject that exception, improving control and accountability.

**Remediation Guidance**
For committed secrets that have already been exposed, GitHub provides context and guidance to help teams revoke, rotate, and resolve the issue efficiently.

**Copilot-powered Detection for Generic Passwords**
Some secrets, especially unstructured or generic passwords, are difficult to identify using traditional pattern matching. GitHub uses AI-powered detection to improve coverage for these secret types without requiring a separate GitHub Copilot license.

**Partner Program**
GitHub scans public repositories for partner token formats used by cloud and service providers. When a supported partner secret is found, GitHub can notify the provider so the credential can be revoked quickly.

**Secret Risk Assessment**
Secret Risk Assessment provides a free scan to help customers evaluate the extent of secret exposure across repositories and better understand current risk.
