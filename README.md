# UkilApa — Women-Centric Digital Legal Aid & Support Platform

**Making legal information and support more accessible for women in Bangladesh.**

UkilApa is a proposed women-centric digital platform designed to help women in Bangladesh understand their preliminary legal options, prepare for legal consultations, discover lawyers, and report incidents of violence through a structured, privacy-conscious workflow.

Developed as a Software Engineering course project, UkilApa combines AI-assisted legal information with practical digital tools to make the first steps toward legal support simpler and more organized.

> **Project status:** Student project / Minimum Viable Product (MVP) in development planning. Features and technologies described below represent the proposed scope and may evolve during implementation.

## Table of Contents

- [Problem Statement](#problem-statement)
- [Our Solution](#our-solution)
- [Key Features](#key-features)
- [Target Users](#target-users)
- [Proposed Technology Stack](#proposed-technology-stack)
- [High-Level Architecture](#high-level-architecture)
- [Privacy, Safety and Responsible AI](#privacy-safety-and-responsible-ai)
- [Project Scope](#project-scope)
- [Getting Started](#getting-started)
- [Project Objectives](#project-objectives)
- [Future Enhancements](#future-enhancements)
- [Academic Information](#academic-information)

## Problem Statement

Women in Bangladesh may encounter legal challenges involving domestic violence, dowry-related violence, divorce and maintenance, child custody, sexual harassment, child marriage, inheritance disputes, and gender-based discrimination.

Finding reliable, understandable legal information and identifying appropriate support can be difficult. Potential clients may also struggle to organize their case details before consulting a lawyer. Witnesses and community members who observe violence may not know how to submit a report or follow up through an appropriate support channel.

UkilApa aims to address these challenges through a centralized digital platform that connects preliminary legal information, case preparation, lawyer discovery, and structured incident reporting.

## Our Solution

UkilApa proposes two connected pathways:

**1. Legal Assistance**
- Access preliminary, AI-assisted legal information.
- Generate and edit a structured summary of a legal issue.
- Discover lawyers based on their practice areas.
- Submit consultation requests and track their status.

**2. Violence Reporting and Referral**
- Allow women and witnesses to report incidents of violence against women.
- Generate a unique report ID for successful submissions.
- Enable authorized reviewers to assess reports and update their status.
- Support referrals to appropriate authorities or support organizations where verified referral processes exist.

The platform is planned as a responsive web application with a mobile-friendly interface.

## Key Features

### 1. AI-Assisted Legal Information
An AI chatbot designed to explain selected women-related legal topics in plain language using a curated knowledge base of Bangladeshi legal resources.

- Source-grounded responses where references are available.
- Clear notices that responses provide preliminary information, not definitive legal advice.
- Safe fallback responses when a question falls outside the supported scope.

### 2. AI-Assisted Case Summary
Helps users organize their legal concerns before seeking professional assistance.

- Generates a structured draft from the user's description.
- Organizes key facts, relevant timelines, parties involved, and questions for a lawyer.
- Allows users to review and edit the summary before saving or sharing it.

### 3. Lawyer Discovery
Helps users identify legal professionals whose listed practice areas match their needs.

- Browse lawyer profiles.
- Filter lawyers by practice area.
- Submit consultation requests.
- View consultation request status.

### 4. Violence Reporting System
Enables women and witnesses to submit reports about observed or experienced incidents of violence.

- Incident category and description.
- Approximate location and date/time.
- Optional supporting evidence.
- Unique report ID after successful submission.
- Report status tracking for the reporter and authorized review workflow.

**Important:** Submitting a report through UkilApa does not automatically contact the police or guarantee an emergency response.

### 5. Administrator and Reviewer Dashboard
Provides authorized personnel with tools to manage platform operations.

- Manage user accounts and lawyer listings.
- Maintain curated legal resources.
- Review and categorize submitted reports.
- Update report and referral statuses.
- Maintain audit records for sensitive status changes.

### 6. Responsive and Accessible Interface
A mobile-friendly experience designed to make core features accessible on common desktop and mobile screen sizes, with Bangla and English support for core navigation where feasible.

## Target Users

| User role | Main capabilities |
|---|---|
| Women / Clients | Ask legal questions, prepare case summaries, discover lawyers, request consultations, and submit or track reports. |
| Witnesses / Community Members | Review safety guidance, submit incident reports, and check report status. |
| Lawyers | Manage professional profiles, specify practice areas, and handle consultation requests. |
| Administrators / Reviewers | Manage users and resources, review reports, and update referral and status records. |

## Proposed Technology Stack

The following technologies are proposed for the project. The final implementation may differ.

| Component | Proposed technology |
|---|---|
| Frontend | React, responsive CSS, optionally Tailwind CSS |
| Mobile approach | Responsive web application / PWA-first; React Native if time permits |
| Backend API | Node.js and Express |
| AI service | Python and FastAPI |
| AI approach | Retrieval-Augmented Generation (RAG) |
| Database | PostgreSQL |
| Evidence storage | Protected local storage for demonstration or private object storage |
| API testing | Postman |
| Automated testing | pytest and the selected backend testing framework |
| Version control | Git and GitHub |

## High-Level Architecture

The proposed system follows a modular architecture that separates the user interface, business logic, AI functionality, and data storage.

```text
              User Interface
                    |
                    v
                REST API
                    |
          +---------+---------+
          |         |         |
          v         v         v
      User &     Lawyer &   Reporting &
      Access     Requests   Admin Services
          |         |         |
          +---------+---------+
                    |
                    v
               PostgreSQL
                    |
                    +------------------+
                    |                  |
                    v                  v
              AI / RAG Service   Protected File Storage
                    |
                    v
          Curated Legal Knowledge Base
```

The AI service is intended to retrieve relevant information from curated legal resources before generating a response. Sensitive records and supporting evidence must be protected through appropriate access controls.

## Privacy, Safety and Responsible AI

Because the platform may handle sensitive legal information and reports of violence, privacy and user safety are core design requirements.

- **Responsible AI:** AI-generated information must be presented as preliminary and must not replace qualified legal advice.
- **Source transparency:** Responses should include relevant legal references when available and avoid unsupported claims.
- **Access control:** Client records, case summaries, and supporting evidence must not be publicly accessible.
- **User control:** Users should be able to review generated case summaries before sharing them.
- **Report protection:** Reports should remain accessible only to the reporter and authorized reviewers according to implemented permissions.
- **Responsible review:** Reports are unverified submissions until assessed; the system must not treat allegations as established facts.
- **Secure development:** The implementation should use appropriate authentication, authorization, protected storage, secure transport, input validation, and data-retention controls.

UkilApa is not intended to determine legal liability, verify allegations automatically, dispatch police, or guarantee confidentiality beyond its actual security controls.

## Project Scope

### Included in the proposed MVP

- Role-based registration and login.
- AI-assisted legal information chatbot.
- Structured case-summary generation.
- Lawyer directory and practice-area filtering.
- Consultation requests and status updates.
- Violence reporting and unique report IDs.
- Report tracking and authorized review.
- Administrative management tools.

### Outside the initial MVP

- Automated police dispatch or guaranteed emergency response.
- AI-based verification of allegations or prediction of legal outcomes.
- Court filing and full-scale case management.
- Full online payment processing and video hearings.
- Guaranteed lawyer availability.
- Unverified direct integration with government or NGO systems.

## Getting Started

The repository's setup instructions will be finalized alongside the actual implementation.

### Prerequisites

The proposed stack may require:

- Node.js and npm for the frontend and backend.
- Python and pip for the AI service.
- PostgreSQL for database management.
- Git for version control.

### Installation

Clone the repository:

```bash
git clone <repository-url>
cd <repository-folder>
```

Install dependencies and configure environment variables according to the individual service instructions once the project structure is established.

**Configuration and execution:** Detailed commands, environment-variable requirements, database setup, API documentation, and testing instructions will be added after the initial application structure is implemented.

Never commit API keys, database passwords, authentication secrets, or real user records to the repository.

## Project Objectives

The proposed MVP will be evaluated against measurable targets:

- Test AI responses against at least 30 prepared questions from supported legal topics, targeting at least 80% with a relevant approved source or a safe fallback/escalation response.
- Generate a structured draft case summary in at least 9 out of 10 test cases.
- Successfully generate a unique report ID for at least 95% of valid end-to-end report submissions in the test environment.
- Complete at least 95% of standard non-AI requests within 3 seconds under a test load of 50 concurrent simulated users.
- Conduct usability testing with at least five test users and document fixes for critical usability and privacy issues before the final demonstration.

These are prototype evaluation targets, not guarantees of legal accuracy or production-level performance.

## Future Enhancements

Potential improvements beyond the initial MVP include:

- Expanded Bangla-language support and voice guidance.
- Improved accessibility for users with limited literacy.
- Carefully evaluated low-identification access options.
- Appointment scheduling and secure video consultations.
- Expanded and regularly reviewed legal knowledge resources.
- Verified referral partnerships with NGOs, women's organizations, legal aid institutions, and public agencies.
- Additional document-preparation and case-management capabilities.

## Academic Information

**Project:** UkilApa — A Women-Centric Digital Legal Aid & Support Platform for Bangladesh  
**Course:** CSE327 — Software Engineering  
**Section:** 3  
**Group:** 7  
**Institution:** North South University, Bangladesh

### Team Members

- Sudipta Karmaker
- Tahsina Mamun Niha
- Raisa Jarin Islam
- Mekdad Hossain Abir

### Disclaimer

UkilApa is an academic software-engineering project. It is intended to support access to preliminary legal information and organize pathways toward professional assistance. It does not provide a substitute for advice from a qualified lawyer, verify allegations of violence, or guarantee emergency intervention. Real-world deployment would require legal review, robust privacy and safeguarding measures, verified referral procedures, and appropriate institutional partnerships.

---

**UkilApa — A safer, simpler first step toward legal support.**
