Version: NAFATH-V3
Track: Software

## Overview


A trustworthy AI assistant for a public service depends on several IT fields working together. Software engineering helps maintain a stable API so the mobile app and its backend can communicate reliably as the service evolves. Artificial intelligence enables the assistant to understand questions and generate useful responses, while Retrieval-Augmented Generation (RAG) can ground answers in official government information. Mobile security protects communication between the app and its servers. Networking provides addressing and connectivity for the growing number of citizens and devices using the service. Cybersecurity helps defend the assistant against attacks, including malicious instructions designed to manipulate its behavior. Data management protects citizens’ chat logs and personal information through appropriate privacy controls. These fields must be considered together rather than treated as separate tasks. A failure in one area can affect the reliability, security, or privacy of the whole service. The project team should test and review these controls before launch and throughout future updates.

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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
