# GitHub Advanced Security Administration

## Security Policies
Guide collaborators on maintaining code health, provide resources for responding to vulnerabilities and limit access. <br>
Set policies at the repository, organization, and enterprise levels, allowing or restricting access as needed. <br>

### Why Security Policies Matter?
Security policies maintain your GitHub ecosystem’s integrity by:
- **Guiding workflows:** Secure, standardized processes
- **Reporting clarity:** Clear steps for vulnerability disclosure
- **Access control:** Least-privilege permissions to limit risk
  
### Documentation and Security Settings ###
- **Standardization:** Ensure consistent responses to common issues across the project
- **Compliance:** Follow industry-standard practices required by regions where projects are developed and published
- **Preventing Critical Failure:** Defend against events that threaten development, like publishing trade secrets or intellectual property

## Security Settings
- **Automation:** Dependabot automates parts of the security process, including updating dependencies, and dependency review further automate security by flagging vulnerabilities
- **Manual Interaction:** Documentation and advisories require significant manual interaction to maintain security
- **Security Advisories:** Create advisories to privately discuss and fix security vulnerabilities

## Security Advisories
GitHub Security Advisories provide a historical narrative for users that demonstrates that you understand the nature of the threat, have addressed the immediate threat, and have taken steps to prevent similar threats.

**Understanding > Action > Practices Revision**
<br>

A security advisory should include the following:
- Product, Versions affected and Severity
- Types of security weaknesses addressed by the project owners' actions
- Impact, status of patched and workarounds

## API Access & Integrations:
- **Personal Access Tokens (PATs):** Tied to a user account; simple scripts; broad scope.
- **Installation Tokens:** For GitHub Apps installations; fine-grained permissions.
- **OAuth Tokens:** For OAuth apps; scoped access; requires least privilege.
