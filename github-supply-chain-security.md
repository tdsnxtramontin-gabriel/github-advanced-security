# GitHub Supply Chain Security
Application security is a priority for organizations that need to reduce technical debt and identify vulnerabilities earlier in the software development lifecycle. As part of a shift-left security strategy, GitHub Advanced Security provides dependency management capabilities that help teams understand, monitor, and secure third-party software used in their projects.

GitHub dependency management tools help reduce the security risks and maintenance burden associated with external packages by identifying vulnerable dependencies, tracking dependency changes, and supporting compliance and audit requirements.

# GitHub Tools for Dependencies
GitHub provides several integrated features to improve supply chain security across repositories:
- **Dependency graph:** Maps direct and transitive dependencies based on manifest and lock files.
- **GitHub Advisory Database:** Provides information about known vulnerabilities affecting open source packages.
- **Dependabot:** Detects vulnerable or outdated dependencies and helps automate remediation.
- **Dependency review:** Analyzes dependency changes in pull requests before they reach the default branch.
- **Software Bill of Materials (SBOM):** Exports a machine-readable inventory of project components for compliance and auditing.

## Dependency Graph
The dependency graph is the foundation of GitHub’s dependency security features. The dependency graph identifies all upstream dependencies and public downstream dependents of a repository or package. You can see your repository’s dependencies and some of their properties, like vulnerability information, on the dependency graph for the repository. To generate the dependency graph, GitHub looks at a repository’s explicit dependencies declared in the manifest and lockfiles. When enabled, the dependency graph automatically parses all known package manifest files in the repository and uses this scan to construct a graph with known dependency names and versions. It supports visibility into dependency relationships and helps power other security features, including Dependabot alerts and dependency review.

# GitHub Advisory Database
The GitHub Advisory Database is a security vulnerability database inclusive of Common Vulnerabilities and Exposures (CVEs)s and GitHub originated security advisories for software dependencies.
It contains detailed information about vulnerabilities, including description, severity, and affected package, using CVSS for severity levels, poviding a free, open-source repository of security advisories and enables community contributions.

# Dependabot:
Dependabot automates dependency security and maintenance workflows in GitHub repositories. It relies on the dependency graph and the GitHub Advisory Database to identify known vulnerable dependencies and recommend secure versions. For Dependabot alerts and updates to work correctly, the dependency graph must be enabled for the repository.

Dependabot supports three main capabilities:
- **Dependabot alerts:** Notify you when a repository depends on a vulnerable package.
- **Security updates:** Automatically open pull requests to remediate vulnerable dependencies.
- **Version updates:** Automatically open pull requests to keep supported dependencies up to date on a configured schedule.

## Dependabot Alerts
Dependabot alerts are generated when GitHub detects that a repository depends on a package affected by a known security advisory. Alerts may be triggered by:

- New advisories published in the GitHub Advisory Database
- Changes to the dependency graph
- Pull requests that introduce vulnerable dependencies

### Dependabot Alert Metadata
Dependabot alert metadata can include:

- Severity rating and score
- CVSS base metrics
- *CWE identifiers
- *CVE ID
- GHSA ID

##### Common Weakness Enumeration (CWE):
Acommunity-developed classification system for software and hardware weakness types. It provides a standardized way to describe, identify, and compare security weaknesses.
##### Common Vulnerabilities and Exposures (CVE):
A catalog of publicly disclosed security vulnerabilities. Each vulnerability receives a unique identifier, which helps organizations reference and track known issues consistently across tools and vendors.

# Software Bill of Materials (SBOM):
A Software Bill of Materials (SBOM) is a formal, machine-readable inventory of a project's dependencies and associated information (such as versions, package identifiers, and licenses). You can use it as part of your audit process and use them to comply with regulatory and legal requirements.
- A machine-readable inventory of a project's dependencies, helping identify vulnerabilities and ensure compliance with data protection standards.
- Can be exported via the GitHub UI or REST API, useful for audits and regulatory requirements.

# Dependency review:
You can use dependency review to catch vulnerable dependencies before they're added to your main branch. Dependency review helps you understand dependency changes and the security impact of these changes at every pull request. It provides an easily understandable visualization of dependency changes with a rich diff on a pull request's Files Changed tab. By checking the dependency reviews in a pull request and changing any dependencies that are flagged as vulnerable, you can avoid vulnerabilities being added to your project. 

Summary: Where Dependabot is more about automatically monitoring and updating known dependencies, dependency review proactively analyzes dependency changes during pull request to highlight key information, like insecure dependencies, enabling you to keep your project safer. Together, these complementary tools can be used to maintain a more secure and up-to-date codebase.
- Catches vulnerable dependencies before they are added to the main branch by analyzing changes in pull requests.
- Shows which dependencies were added, removed, or updated, along with their release dates and vulnerability data.

# Dependabot security updates:
Dependabot alerts notify you of vulnerabilities in your repository.
Dependabot security updates are automated pull requests that help you update dependencies with known vulnerabilities.
Dependabot version updates are automated pull request that keep your dependencies updated, even when they don't have any vulnerabilities.

# GitHub Actions Dependency Review
Helps you understand dependency changes and their security implications at every pull request.
Shows which dependencies were added, removed, or updated, and provides vulnerability data for these dependencies.
Analyzes dependency changes to prevent insecure dependencies from entering the project, complementing Dependabot's role in keeping dependencies patched and up to date.
