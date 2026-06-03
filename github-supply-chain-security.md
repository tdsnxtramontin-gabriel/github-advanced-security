# GitHub Supply Chain Security
Application security is a priority for organizations that need to reduce technical debt and identify vulnerabilities earlier in the software development lifecycle. As part of a shift-left security strategy, GitHub Advanced Security provides dependency management capabilities that help teams understand, monitor, and secure third-party software used in their projects. GitHub Supply Chain Security help reduce the security risks and maintenance burden associated with external packages by identifying vulnerable dependencies, tracking dependency changes, and supporting compliance and audit requirements.

# GitHub Tools for Dependencies
GitHub provides several integrated features to improve supply chain security across repositories:
- **Dependency graph:** Maps direct and transitive dependencies based on manifest and lock files.
- **GitHub Advisory Database:** Provides information about known vulnerabilities affecting open source packages.
- **Dependabot:** Detects vulnerable or outdated dependencies and helps automate remediation.
- **Dependency review:** Analyzes dependency changes in pull requests before they reach the default branch.
- **Software Bill of Materials (SBOM):** Exports a machine-readable inventory of project components for compliance and auditing.

## Dependency Graph
The dependency graph is the foundation of GitHub’s dependency security features. The dependency graph identifies all upstream dependencies and public downstream dependents of a repository or package. You can see your repository’s dependencies and some of their properties, like vulnerability information, on the dependency graph for the repository. To generate the dependency graph, GitHub looks at a repository’s explicit dependencies declared in the manifest and lockfiles. When enabled, the dependency graph automatically parses all known package manifest files in the repository and uses this scan to construct a graph with known dependency names and versions. It supports visibility into dependency relationships and helps power other security features, including Dependabot alerts and dependency review.

## GitHub Advisory Database
The GitHub Advisory Database is a security vulnerability database inclusive of CVEs and GitHub originated security advisories for software dependencies.
It contains detailed information about vulnerabilities, including description, severity, and affected package, using CVSS for severity levels, poviding a free, open-source repository of security advisories and enables community contributions.

## Dependabot:
Dependabot automates dependency security and maintenance workflows in GitHub repositories. It relies on the dependency graph and the GitHub Advisory Database to identify known vulnerable dependencies and recommend secure versions. For Dependabot alerts and updates to work correctly, the dependency graph must be enabled for the repository.

Dependabot supports three main capabilities:
- **Dependabot alerts:** Notify you when a repository depends on a vulnerable package.
- **Security updates:** Automatically open pull requests to remediate vulnerable dependencies.
- **Version updates:** Automatically open pull requests to keep supported dependencies up to date on a configured schedule.

## Dependabot Alerts
Dependabot alerts are generated when GitHub detects that a repository depends on a package affected by a known security advisory. Alerts may be triggered by:

- New advisories published in the GitHub Advisory Database.
- Changes to the dependency graph.
- Pull requests that introduce vulnerable dependencies.

### Dependabot Alert Metadata
Dependabot alert metadata can include:

- Severity rating and score.
- CVSS base metrics.
- CWE identifiers.
- CVE ID.
- GHSA ID.

## Dependabot Updates
Dependabot provides two types of automated pull requests:

- **Security updates:** Address dependencies with known vulnerabilities.
- **Version updates:** Keep dependencies current even when no vulnerability is currently known.

These update mechanisms help maintain a healthier dependency ecosystem and reduce long-term maintenance risk.

## Dependency Review:
You can use dependency review to catch vulnerable dependencies before they're added to your main branch. Dependency review helps you understand dependency changes and the security impact of these changes at every pull request. Dependency review helps prevent vulnerable dependencies from being merged into the default branch. It analyzes dependency changes in pull requests and highlights the security impact before the change is accepted. It provides an easily understandable visualization of dependency changes with a rich diff on a pull request's Files Changed tab. This makes dependency review a proactive control, while Dependabot serves as a monitoring and remediation mechanism.

## GitHub Actions Dependency Review
GitHub Actions can be used to automate dependency review during pull request workflows. This helps enforce security checks before merging code changes. It shows which dependencies were added, removed, or updated, and provides vulnerability data for these dependencies.

With GitHub Actions dependency review, teams can:
- Detect dependency changes in pull requests.
- Identify insecure or vulnerable packages before merge.
- Add automated checks to CI workflows.
- Strengthen policy enforcement for dependency security.

## Software Bill of Materials (SBOM):
A Software Bill of Materials (SBOM) is a formal, machine-readable inventory of a project's dependencies and associated information (such as versions, package identifiers, and licenses). You can use it as part of your audit process and use them to comply with regulatory and legal requirements. GitHub supports exporting SBOM data through the user interface and REST API.

## Glossary
- **Common Vulnerability Scoring System (CVSS):** A standardized framework used to measure the severity of a security vulnerability. 
- **Common Weakness Enumeration (CWE):** A community-developed classification system for software and hardware weakness types that provides a standardized way to describe, identify, and compare security weaknesses.
- **Common Vulnerabilities and Exposures (CVE):** A catalog of publicly disclosed security vulnerabilities where each vulnerability receives a unique identifier, which helps organizations reference and track known issues consistently across tools and vendors.
