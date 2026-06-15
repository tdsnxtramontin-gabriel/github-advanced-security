# GitHub Code Security
GitHub Code Security brings together multiple application security capabilities directly within GitHub. Its purpose is to help organizations identify vulnerabilities in both the code they develop and the third-party components they depend on. At a high level, Code Security spans two major areas of application security testing: Static Application Security Testing (SAST) and Software Composition Analysis (SCA).

## What is Code Scanning?
Code scanning uses CodeQL, a static-analysis tool, to analyze the code in a GitHub repository to find security vulnerabilities and coding errors. Code scanning is available for all public repositories, and for private repositories owned by organizations where GitHub Advanced Security is enabled. If code scanning finds a potential vulnerability or error in your code, GitHub displays an alert in the repository's Security tab. After you fix the code that triggered the alert, GitHub closes the alert. You can use code scanning to find, triage, and prioritize fixes for existing problems in your code. Code scanning also prevents developers from introducing new problems. You can schedule scans for certain days and times, or trigger scans when a specific event occurs in the repository, such as a push.

## SAST vs SCA
Static Application Security Testing (SAST) focuses on identifying vulnerabilities in first-party code before an application is deployed. Software Composition Analysis (SCA) focuses on risks introduced through dependencies, including open-source packages and third-party components. Since a large share of modern applications relies on open source, both areas are essential to securing the software supply chain. In practical terms, GitHub Code Security helps customers assess both the code they write and the external components they rely on. GitHub’s SAST capability is powered by CodeQL, while dependency and supply chain risk detection is supported through Dependabot.

## GitHub's SAST solution: CodeQL
CodeQL is GitHub’s semantic code analysis engine for identifying security vulnerabilities in source code. While Secret Protection focuses on exposed credentials, CodeQL detects a broader range of security issues, from common coding flaws to more complex vulnerability patterns. It works by analyzing code as data, enabling deep and precise security analysis across supported languages and frameworks. It combines expert-built security queries with the flexibility for organizations to create their own custom queries. This allows teams to tailor analysis to their environment, coding standards, and threat model.

**Language and Framework Support**
<br>
GitHub Code Security provides broad language coverage through native CodeQL analysis as well as support for third-party tool integration. CodeQL supports major languages such as Java, JavaScript, TypeScript, Python, Go, Ruby, C, C++, and C#. For each language, GitHub provides specialized query coverage aligned to language-specific risks, frameworks, and security patterns, improving relevance and accuracy across different technology stacks.

**Query Management**
<br>
Query management enables organizations to customize the CodeQL analysis used in their environments. Teams can enable or disable query suites, create custom queries, manage versions, and share query logic across repositories. This helps align security testing with internal standards, business requirements, and the organization’s specific risk profile.

## GitHub's SCA solution: Dependabot
Dependabot helps organizations identify vulnerable dependencies before they introduce risk into production environments. It is integrated into the pull request workflow, giving developers visibility into dependency-related issues before code is merged. Dependabot also simplifies remediation by linking to vulnerability intelligence and recommending safer package versions where available. Another important capability is auto-triage, which helps teams automatically classify and prioritize dependency alerts based on predefined policies. This reduces manual effort and helps security teams focus on the most important vulnerabilities across repositories. It is also worth noting that Dependabot is included in GitHub Enterprise plans at no additional cost.

**Exploit Prediction Scoring System (EPSS)**
<br>
Dependabot alerts can include EPSS data from FIRST, the Forum of Incident Response and Security Teams. EPSS helps organizations prioritize remediation by estimating the likelihood that a vulnerability will be exploited in the next 30 days. The score is presented together with a percentile ranking, giving teams additional context for risk-based decision-making.

**Multi-Repository Variant Analysis (MRVA)**
<br>
Multi-Repository Variant Analysis helps security teams identify similar vulnerability patterns across multiple repositories at once. When a new class of vulnerability is discovered, MRVA can be used to quickly locate related instances across the organization’s codebase, even when the implementation differs between projects. This supports faster incident response and helps uncover broader, systemic issues.
