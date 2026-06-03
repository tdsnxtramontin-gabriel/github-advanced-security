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
- Dependency review: Tracks dependency changes and checks for known vulnerabilities in every pull request.

## Define GHAS features
GitHub’s security features collectively helped developers and security teams work together to maintain a secure and compliant codebase.

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
