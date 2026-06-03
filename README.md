# Understand GHAS and its role in the Security Ecosystem
GitHub Advanced Security (GHAS) plays a crucial role in enhancing the security posture of software development projects on GitHub. It provides a comprehensive set of tools and features designed to identify and address security vulnerabilities throughout the development lifecycle. GHAS is primarily used by organizations running on GitHub Enterprise Cloud, offering enterprise-grade security features such as code scanning, secret scanning, and automated dependency management.

- **Early Detection:** Integrating security early allows for the detection of vulnerabilities at the source code level.
- **Efficient Remediation:** Security issues can be addressed promptly as part of the regular development activities.
- **Security Standards:** Integration ensures consistent adherence to security standards across the SDLC.

# What is GitHub Advanced Security?

## Software Development Cycle

**01. Basic Security Scenario:**

![](./images/basic-approach.png)

- Traditional Approach: Security tests are conducted during the quality-assurance phase, often causing delays.
- Bottleneck: Security becomes a bottleneck, hindering the timely release of Software.
- Shift Left: The goal is to integrate security earlier in the development process to avoid these delays.

<br>**02. GitHub Advanced Security Scenario:**

In this scenario, security is set up right from the beginning through security policies at the project configuration stage:

![](./images/GHAS-approach.png)

- Code scanning: Scan at every commit and merge for potential vulnerabilities and coding errors.
- Secret scanning: Scan for tokens and private keys that were accidentally committed.
- Dependency review: Tracks project dependency changes and checks for known vulnerabilities in every pull request.

## Define GHAS features

**Secret Scanning:**
- Identifies and mitigates exposure of sensitive information like API keys and tokens.
- Searches for predefined patterns and signatures to detect sensitive data.
- Includes push protection to prevent secret leaks and easy alert remediation within GitHub.

**Code Scanning:**
- Analyzes source code for security vulnerabilities and coding errors using static analysis.
- Enhances security by identifying issues early and improves code quality.
- Provides automated feedback within the pull request workflow to address vulnerabilities.

**Dependabot:**
- Manages project dependencies by checking for updates and opening pull request.
- Ensures projects have recent security patches and automates dependency updates for secure development.
- Dependency Review to check for vulnerable dependencies within a pull request before merging.


# GitHub Secret Protection

# GitHub Code Security

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
