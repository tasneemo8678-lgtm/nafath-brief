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
Under Semantic Versioning, whenever there’s a change in the assistant’s public API that breaks backward compatibility—like altering or removing an endpoint that existing applications depend on—you need to bump up the MAJOR version. If you’re adding new features but everything continues to function well with older versions, that’s the time to increase the MINOR version. This organized method helps developers implement updates with confidence, reducing the chances of running into unexpected problems.

Resource: Semantic Versioning 2.0.0 - https://semver.org/spec/v2.0.0.html

## AI
Retrieval augmented generation, or RAG for short, is a cool blend of information retrieval and AI text generation. Before the assistant jumps in with an answer, it first digs up relevant information from reliable sources, like government service pages. This way, it can craft a response that's more accurate and grounded. It’s a step up from just relying on what’s stored in the model’s memory, but it’s still super important to ensure the quality and verification of those sources.

Resource: Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks - https://arxiv.org/abs/2005.11401

## Mobile
iOS App Transport Security (ATS) is all about keeping your connections secure by mandating HTTPS for every network request. If an app attempts to access a plain HTTP endpoint, ATS will automatically block that request. This is a great way to ensure that privacy and data integrity are maintained between the app and its servers. Developers are encouraged to set up their servers for HTTPS instead of compromising ATS protections with exceptions.

Resource: Preventing Insecure Network Connections - https://developer.apple.com/documentation/security/preventing-insecure-network-connections

## Networking
IPv4 uses 32-bit addresses, which limits the number of unique devices that can connect to the internet. On the other hand, IPv6 makes a significant advancement with its 128-bit addresses, providing a vast address space. This is especially important as more individuals are using smartphones, computers, and IoT devices to access public services. Additionally, IPv6 simplifies autoconfiguration and routing, making networks more scalable and reliable as demand keeps growing

Resource: RFC 8200: RFC 8200: Internet Protocol, Version 6 (IPv6) Specification — https://www.rfc-editor.org/rfc/rfc8200

## Cybersecurity
Prompt injection is a sneaky tactic that attackers use to trick an AI assistant into executing harmful commands. There are two main types: direct prompt injection, where the malicious text is fed straight into the assistant, and indirect prompt injection, which cleverly hides harmful instructions within external data, like a webpage. To reduce these risks, developers can set up filters for inputs and restrict the external sources that the assistant is allowed to engage with.

Resource: OWASP Top 10 for LLM Applications — https://owasp.org/www-project-top-10-for-llms (owasp.org in Bing)

## Data
Anonymization wipes out all identifiers, making it impossible to trace the data back to an individual, which means it falls outside the realm of data protection laws. On the other hand, pseudonymization swaps out identifiers for codes, allowing for re-identification if you have access to the mapping, so it still falls under data protection regulations. When it comes to storing chat logs, anonymization provides a higher level of privacy, while pseudonymization allows for analysis with restricted access.

Resource: GDPR Article 4 — Definitions of Personal Data, Anonymization, and Pseudonymization — https://gdpr-info.eu/art-4-gdpr

## Misconception in My Track
One common misunderstanding in the world of software engineering is the belief that any tweak to the API automatically calls for a MAJOR version increase. However, according to the rules of Semantic Versioning, a MAJOR version bump is only necessary when changes disrupt backward compatibility. This typically happens when you remove or modify an endpoint in a way that existing applications can no longer work with it. If you're adding new features that still play nicely with the old ones, you should bump up the MINOR version instead. And for those pesky bug fixes? They just require a PATCH update. You can find this important distinction laid out in the “Specification” section of Semantic Versioning 2.0.0.
Resource evidence: Semantic Versioning 2.0.0, section 8 - https://semver.org/spec/v2.0.0.html

## Open Question
How can the project team automatically test API compatibility before releasing a new version, so that mobile app updates do not unexpectedly break existing users?
