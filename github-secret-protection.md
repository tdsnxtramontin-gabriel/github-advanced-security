# GitHub Secret Protection
GitHub Secret Protection helps organizations detect, prevent, and remediate exposed secrets across the software development lifecycle. In application security, a secret is any sensitive credential or confidential value that grants access to systems, services, or data, such as API keys, access tokens, passwords, and cloud credentials. GitHub Secret Protection also includes supporting features that improve governance, response, and detection coverage. From a Business perspective, Secret Protection reduces the risk of security incidents caused by accidental credential exposure. From a Technical perspective, it provides automated detection, prevention, and response workflows directly within the developer experience.

## What is Secret Scanning?
Secret scanning automatically scans your entire Git history on all branches present in your GitHub repository for any secrets. When a secret with a known pattern is committed into a private or public repository in your project, secret scanning sends a notification to all repository administrators about the commit that contains the secret. Repository administrators can then view the list of all detected secrets in the repository's Security tab. GitHub also notifies the service provider who issued the secret if they're partnered with GitHub.

### **Coverage**  
Secret scanning can detect secrets in:
- **Commits and repository history**
- **Issues**: titles, descriptions, and comments
- **Pull requests**: titles, descriptions, and comments
- **GitHub Discussions**: titles, descriptions, and comments

### **Availability**
- **Public Repositories:** Enabled by default and cannot be turned off. Alerts are available for free.
- **Private Repositories:** Requires manual enabling and a GitHub Advanced Security license for secret scanning.

## What is Push Protection?
Push Protection stops supported secrets before they are pushed to the repository, prompting contributors to remove or bypass detected secrets before it becomes part of the codebase or commit history
- **Default settings:** Enabled by default for public projects to prevent accidental secret leaks.
- **User Experience:** Provides remediation guidance directly in the IDE or command-line interface.

### **Enablement**
- **Repository Level:** Navigate to Settings > Code security and analysis, enable GitHub Advanced Security, Secret Scanning, and Push Protection.
- **Organization Level:** Enable GitHub Advanced Security and Secret Scanning for all private repositories, with options for automatic enabling on new repositories.
  
## **Key Features**

**Validity Check**  
GitHub can validate whether a detected secret is still active, helping teams prioritize real exposure and reduce false positives. <br>
- Improves triage efficiency and focuses remediation efforts on active threats
- Supports faster, risk-based incident response
<br>

**Remediation Guidance**  
Provides guidance on what to do after a secret is exposed. <br>
- Supports faster response and cleanup
- Improves consistency in incident handling
<br>

**Copilot-powered Detection for Generic Passwords**  
Uses AI-powered detection to identify hard-to-detect credentials <br>
- Extends detection beyond structured secret formats
- Does not require a separate GitHub Copilot license for this capability
<br>

**Custom Patterns**  
Allow organizations to define their own secret-detection patterns for proprietary or company-specific credentials not covered by GitHub’s default detectors.
- Supports up to 500 custom patterns per organization/enterprise account, and up to 100 per private repository.
- Enables better alignment with internal security policies
<br>

**Partner Program**  
When GitHub detects supported partner tokens in public repositories, it can notify the secret provider directly.
- Strengthens ecosystem-level response
- Reduces the exposure window
<br>

**Secret Risk Assessment**  
Provides a free assessment to help organizations understand the scope of secret exposure across repositories.
- Helps identify current risk levels to support prioritization and planning
- Useful as an entry point for security maturity discussions
<br>

**Delegated Bypass**  
Allows developers to request an exception when a push is blocked, with approval routed to designated reviewers.
- Adds control and accountability to bypass decisions
- Supports governance and creates an auditable exception workflow
