# SBOM
**SBOM** stands for **Software Bill of Materials**.

Think of it like the **ingredient list on a food package**, but for software.

An SBOM is a formal inventory that lists:

- All software components used in an application
- Open-source libraries and dependencies
- Third-party packages
- Versions of each component
- Supplier or publisher information
- Relationships between components

#### Example
Suppose your application depends on:
```
MyWebApp 1.0
├── Spring Boot 3.2
│   ├── Jackson 2.17
│   └── Logback 1.5
├── PostgreSQL JDBC Driver 42.7
└── OpenSSL 3.3
```
The SBOM records this dependency information in a **machine-readable format**.


## Why is SBOM important?
### 1. Security

When a vulnerability is announced, you can quickly determine whether your software is affected.

For example, when the Log4Shell vulnerability was discovered in Log4j in 2021, organizations with SBOMs could rapidly identify which applications contained vulnerable versions of Log4j.

### 2. Compliance

Many organizations and governments now require software suppliers to provide SBOMs as part of the software supply chain security process.

### 3. License Management

SBOMs help track open-source licenses:

- MIT
- Apache 2.0
- GPL
- BSD

This helps companies avoid license compliance issues.

### 4. Vulnerability Management

Security tools can compare SBOM contents against vulnerability databases (such as CVE databases) to find known security issues.

## Common SBOM Formats
### SPDX

Created by the Linux Foundation.

Example:
```
SPDXID: SPDXRef-Package
PackageName: log4j-core
PackageVersion: 2.14.1
```
