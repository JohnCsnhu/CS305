Overview

This repository contains my submission for CS 305: Software Security – Project Two. The artifact included is the Practices for Secure Software Report, which documents how I identified vulnerabilities and implemented secure coding practices for the client, Artemis Financial.

Artemis Financial is a consulting firm that builds customized financial plans (savings, retirement, investments, and insurance). As part of modernizing their software, they required secure communication and integrity checks to protect sensitive client data.

Reflection

Artemis Financial asked me to improve the security posture of their software, with a focus on protecting data in transit and verifying data integrity. Concretely, I implemented HTTPS/TLS for secure transport and checksum verification (SHA-256) to ensure files/data were not tampered with. I also performed a dependency vulnerability assessment.

Systematically, I've identified and triaged dependency vulnerabilities, prioritized fixes, and verified that remediation did not break functionality. Coding securely reduces the risk of exploits, protects client trust, and supports regulatory/compliance expectations in finance. For a company like Artemis Financial, strong software security directly supports business continuity and reputation.

The most challenging element was interpreting vulnerability scan results, especially separating true risk from false positives and understanding the impact of transitive dependencies. Working through this improved my ability to read CVEs, check affected versions, and map findings to specific libraries actually used by the application.

Added layered controls by enabling HTTPS/TLS (disabling plain HTTP), enforcing strong cryptography for data integrity via SHA-256 checksums, and tightening dependency hygiene. Going forward, I would combine SCA (OWASP Dependency-Check or Snyk) with SAST (SpotBugs + FindSecBugs) and DAST (OWASP ZAP) to assess vulnerabilities end-to-end, then choose mitigations based on severity, exploitability, and business impact.

Keeping the code functional and secure; checking for new issues after refactoring. After each change, I verified normal application behavior (manual tests of critical paths/endpoints) and re-ran the vulnerability scan to confirm no new issues were introduced. I validated HTTPS with connection tests and ensured checksum verification correctly detected altered content. This loop—change → test → rescan—helped keep the software both secure and functional.

Using OWASP Dependency-Check (Maven) to generate reports, strong TLS/HTTPS configuration, and SHA-256 via standard cryptographic libraries for integrity checks. I followed OWASP guidance (ASVS/Cheat Sheets) for secure configuration and dependency management. These practices—secure transport, integrity verification, and continuous scanning—are broadly applicable to future coursework and professional projects.

From this assignment I can share with an employer the secure-coding write-up explaining threats and mitigations, the before/after dependency-check reports showing reduced risk, and the configuration and code changes that enabled HTTPS and checksum verification. Together, these demonstrate practical skills in finding, fixing, and documenting software security issues while preserving functionality.
