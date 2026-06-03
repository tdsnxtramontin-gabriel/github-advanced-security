# GitHub Advanced Security Administration

## Setting Security Policies
Guide collaborators on maintaining code health, provide resources for responding to vulnerabilities and limit access. <br>
Set policies at the repository, organization, and enterprise levels, allowing or restricting access as needed. <br>

**Documentation and Security Settings:**
- Standardization: Ensure consistent responses to common issues across the project.
- Compliance: Follow industry-standard practices required by regions where projects are developed and published.
- Preventing Critical Failure: Defend against events that threaten development, like publishing trade secrets or intellectual property.

**Documentation:**
- Community Health Files: Create default files like README.md, CODE_OF_CONDUCT.md and CONTRIBUTING.md to guide collaborators.
- Security Information: Record security preparation, key contacts and project background to inform collaborators and users.

**Security.md:**
- Purpose: Communicate security information and instructions for reporting vulnerabilities.
- Content: Include supported versions, reporting methods, compliance information, security technologies and known risks.
- Location: Place in the repository's root, docs or .GitHub folder.

## Setting Security Settings
- Automation: Dependabot automates parts of the security process, including updating dependencies, and dependency review further automate security by flagging vulnerabilities.
- Manual Interaction: Documentation and advisories require significant manual interaction to maintain security.
- Security Advisories: Create advisories to privately discuss and fix security vulnerabilities.

## Manage GHAS alerts
- Organization Level: Displays aggregate and repository-specific security information for all repositories owned by the organization.
- Team Level: Shows repository-specific security information for repositories where the Team has admin privileges.
- Repository Level: Indicates which security features are enabled and provides options to configure any available but unused features.
