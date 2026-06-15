# GitHub Code Security
GitHub Code Security brings together multiple application security capabilities directly within GitHub. Its purpose is to help organizations identify vulnerabilities in both the code they develop and the third-party components they depend on. At a high level, Code Security spans two major areas of application security testing: Static Application Security Testing (SAST) and Software Composition Analysis (SCA).

## What is Code Scanning?
Code scanning is GitHub’s SAST capability. It analyzes source code in a repository to identify security vulnerabilities and coding errors. GitHub’s native code scanning experience is powered by CodeQL, GitHub’s semantic code analysis engine. When code scanning detects a potential issue, GitHub creates an alert in the repository’s Security tab. Teams can then investigate, triage, and remediate the finding. Once the underlying issue is fixed, the alert is closed automatically or through the normal remediation workflow. Code scanning can be configured to run on a schedule or in response to repository events such as pushes and pull requests. This allows organizations to continuously assess their codebase and helps prevent new vulnerabilities from being introduced during development.

### Language and Framework Support
GitHub Code Security provides broad language coverage through native CodeQL analysis as well as support for third-party tool integration. CodeQL supports major languages such as Java, JavaScript, TypeScript, Python, Go, Ruby, C, C++, and C#. For each language, GitHub provides specialized query coverage aligned to language-specific risks, frameworks, and security patterns, improving relevance and accuracy across different technology stacks.

### Query Management
Query management enables organizations to customize the CodeQL analysis used in their environments. Teams can enable or disable query suites, create custom queries, manage versions, and share query logic across repositories. This helps align security testing with internal standards, business requirements, and the organization’s specific risk profile.

## Working with CodeQL in Practice
In addition to GitHub’s native code scanning experience, organizations can work directly with CodeQL to prepare databases, run queries, interpret results, and customize analysis workflows. This is especially useful for advanced use cases, non-standard build environments, and integration with external tools.

### Preparing a Database for CodeQL
CodeQL analysis begins with the creation of a database that represents the structure of the codebase being analyzed.

To prepare a database, teams first install and set up the **CodeQL CLI**, then check out the version of the codebase they want to analyze.
- For **compiled languages**, CodeQL extracts relational representations during the build process.
- For **interpreted languages**, the extractor runs directly on the source code.

The CodeQL CLI bundle can be downloaded from the CodeQL public repository’s releases page. After extracting the archive, the `codeql` executable can be used to verify the installation and run analysis commands. Common setup verification commands include `codeql resolve qlpacks` and `codeql resolve languages`

To create a database, teams use:
- `codeql database create <database> --language=<language-identifier>`

Additional options can be provided depending on the language, build process, and environment.

### Extractors and Database Contents
CodeQL uses **extractors** to produce the relational data and source references needed to build a database. Each extractor has its own configuration options, which can be inspected with:

- `codeql resolve extractor --format=betterjson`

A CodeQL database typically contains relational data extracted from the code, copied source files, and a language-specific database schema. At a lower level, the database includes structures such as expressions and statements tables, while the CodeQL libraries provide higher-level abstractions over this data model.

### Running CodeQL Queries
Once a database has been created, teams can run **CodeQL queries** against it to identify vulnerabilities and coding errors. CodeQL supports different query types, including **alert queries**, which identify specific problems in code and **path queries**, which model and visualize how data flows from a source to a sink. A simple CodeQL query is stored in a `.ql` file and typically includes a `select` clause. Queries can also include metadata that describes their purpose, severity, and how results should be interpreted and displayed. CodeQL uses **QL**, a declarative and object-oriented query language designed for analyzing hierarchical program structures. It supports logical formulas, quantifiers, aggregations, and other database-style operations to express complex security logic concisely.

### Understanding CodeQL Results
CodeQL results can be reviewed directly on GitHub or in the **CodeQL extension for Visual Studio Code**, where interpreted results are displayed in the source code context. A typical alert includes the identified problem, the tool that generated the finding, the relevant line of code, severity and security severity, when the issue was introduced, and the nature of the vulnerability or coding error. For many findings, CodeQL also provides guidance on remediation. In data-flow scenarios, path information can help teams understand how untrusted input reaches a dangerous sink.

### Path Queries and Data Flow Analysis
Path queries are particularly useful for investigating security-sensitive flows across a codebase. They help visualize how data moves between sources and sinks, making them valuable for understanding vulnerabilities such as injection flaws, unsafe deserialization, or other taint-style issues. These queries usually include query metadata, predicates that define the data-flow logic, and a `select` statement that returns the relevant path. They may also rely on supporting modules that define the flow model and path graph.

### Troubleshooting and Optimizing CodeQL
As CodeQL adoption grows, organizations often need to optimize both analysis runtime and query performance.

#### Optimizing Query Performance
CodeQL queries are evaluated in a bottom-up manner, and large predicates can generate large intermediate tables that are expensive to compute. Since QL relies on standard database-style operations such as joins, projections, and unions, efficient query design is important for maintaining good performance.

### Debug Artifacts
For deeper troubleshooting, teams can enable debug artifacts in a CodeQL workflow by setting debug mode to `true` in the initialization step. These artifacts can include CodeQL logs, generated databases, and SARIF output files. They are especially useful when diagnosing extraction issues, unexpected findings, or workflow failures.

### Using the CodeQL CLI
Beyond the GitHub web interface, the **CodeQL CLI** provides access to many of the same core capabilities from the command line.

Common commands include:
- `codeql database create` – creates a CodeQL database for a supported language;
- `codeql database analyze` – runs queries against a database and generates results, typically in SARIF format;
- `codeql github upload-results` – uploads SARIF results to GitHub so they appear as code scanning alerts.

SARIF uploads are supported for public repositories and for organization-owned repositories where GitHub Advanced Security is enabled.

### Customizing Languages and Builds for Code Scanning
GitHub code scanning supports multiple languages by default and includes an **autobuild** capability for standard build processes. However, repositories with non-standard build pipelines may require workflow customization.

#### Custom Build Steps
For standard projects in languages such as C/C++, C#, and Java, the **autobuild** action may be sufficient. For non-standard build processes, teams can remove the autobuild step, define manual build commands, and adapt the workflow to match the repository’s actual build requirements. This is often necessary in monorepos, custom CI pipelines, or projects with specialized dependency and compilation steps.

### Enabling Code Scanning with Third-Party Tools
GitHub code scanning also supports results generated outside GitHub, as long as they are provided in **SARIF** format. This allows organizations to integrate third-party static analysis tools and still surface findings in the GitHub code scanning experience. SARIF results can be uploaded through the **code scanning API**, the **CodeQL CLI**, or **GitHub Actions**.

#### Code Scanning API
The code scanning API can be used to retrieve and update information about code scanning alerts, analyses, and configurations. Some endpoints use specific media types such as `application/sarif+json`.

#### GitHub Actions for SARIF Uploads
Organizations can use the `upload-sarif` action in GitHub Actions workflows to publish external analysis results. This is typically configured with parameters such as `sarif-file` and can run on events like pushes or scheduled scans.
