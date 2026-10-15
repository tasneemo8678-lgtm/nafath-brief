Version: NAFATH-V3
Track: Software

## Overview

software engineering keeps the API stable so the mobile app and its backend can communicate reliably as the service grows.
AI helps the assistant understand questions and give useful answers, while retrieval augmented generation (RAG) connects responses to official government information.
mobile security protects communication between the app and its servers.
networking provides addressing and connectivity for the increasing number of citizens and devices using the service.
cybersecurity defends the assistant against attacks, including malicious instructions meant to change its behavior.
data management protects citizens, chat logs and personal information with proper privacy controls. these fields must be considered together, and the team must apply semantic versioning correctly when deciding if API changes require a major, minor, or patch release.

## Software
Under Semantic Versioning, the assistant's public API must increase its MAJOR version when a change breaks backward compatibility. A MINOR version increase is required when new functionality is added in a backward-compatible way. A PATCH version increase is required for backward-compatible bug fixes. For example, removing an API endpoint may require a MAJOR release, adding an optional feature may require MINOR, and fixing an internal error may require PATCH. Clear versioning helps app developers plan updates safely.

Resource: Semantic Versioning 2.0.0 - https://semver.org/spec/v2.0.0.html

## AI
Retrieval-Augmented Generation (RAG) combines information retrieval with AI text generation. Before answering a citizen's question, the assistant retrieves relevant information from a trusted knowledge source, such as official government service pages, and uses that information to generate a response. RAG can reduce incorrect answers by grounding responses in current, relevant evidence instead of relying only on the model's stored knowledge. However, it cannot eliminate errors, so source quality and answer verification remain important.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401

## Mobile
iOS App Transport Security (ATS) improves privacy and data integrity by requiring secure network connections that meet Apple's security requirements. When an app uses standard networking APIs such as URLSession, its HTTP connections must use HTTPS. If the app tries to contact a plain HTTP endpoint, ATS blocks the connection by default, and the request fails. Developers should configure the server for HTTPS rather than weaken ATS protections through exceptions.

Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking
IPv4 uses 32-bit addresses, while IPv6 uses 128-bit addresses, providing a vastly larger address space. As more citizens connect through phones, computers, and smart devices, IPv4 addresses become harder to allocate without additional techniques such as address translation. IPv6 supports a much greater number of uniquely addressable devices and simpler address autoconfiguration. The government service should ensure its network infrastructure supports IPv6 while considering compatibility with IPv4 systems.

Resource: RFC 8200: Internet Protocol, Version 6 (IPv6) Specification - https://www.rfc-editor.org/rfc/rfc8200

## Cybersecurity
Prompt injection occurs when malicious instructions attempt to manipulate an AI system into ignoring its intended rules. Direct prompt injection comes from a user's input, while indirect prompt injection is hidden in external content the assistant retrieves or processes. Two risk-reduction measures are to treat retrieved content as untrusted data and to restrict the assistant's permissions using least privilege. Input screening and testing can help, but no single defense eliminates every attack.

Resource: NIST AI 100-2 E2025: Adversarial Machine Learning - https://csrc.nist.gov/pubs/ai/100/2/e2025/final

## Data
Anonymization removes identifying information so that a person can no longer be identified using means reasonably likely to be used. Pseudonymization replaces direct identifiers with codes or aliases, but a person may still be re-identified using additional information kept separately. Therefore, pseudonymized chat logs remain personal data under the GDPR. Properly anonymized data may fall outside the GDPR's scope if identification is no longer reasonably possible. The government entity should assess re-identification risks before treating logs as anonymous.

Resource: GDPR Article 4 and Recital 26 - https://gdpr-info.eu/art-4-gdpr/

## Misconception in My Track
A common misconception is that every API change requires a MAJOR version increase. In fact, Semantic Versioning distinguishes changes by their compatibility with the existing public API. A backward-compatible bug fix requires a PATCH release, while adding backward-compatible functionality requires a MINOR release. A change that breaks backward compatibility requires a MAJOR release. Therefore, the project team should evaluate compatibility before selecting a version number. The Semantic Versioning specification states: “MAJOR version when you make incompatible API changes.”

Resource evidence: Semantic Versioning 2.0.0, section 8 - https://semver.org/spec/v2.0.0.html

## Open Question
How can the project team automatically test API compatibility before releasing a new version, so that mobile app updates do not unexpectedly break existing users?
