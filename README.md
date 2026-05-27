# MediBuddy

MediBuddy is an AI-powered diagnostic and medical education platform designed to help medical students and junior healthcare professionals practice clinical reasoning through realistic, case-based interactions.

This public repository contains the project documentation and presentation materials for the MediBuddy final year project. It does not currently include the full application source code.

## Repository Access

The application source code is kept private. Ownership is retained by RISETech, NSHS, and the development team.

## Repository Contents

- [FYP Report_Medibuddy.pdf](./FYP%20Report_Medibuddy.pdf) - complete project report covering motivation, architecture, methodology, deployment, and validation.
- [Final Presentation.pdf](./Final%20Presentation.pdf) - presentation deck summarizing the workflow, dataset, deployment, and demo surfaces.
- README.md - project overview for public readers.
- [Project Demo](https://drive.google.com/file/d/1OimYYpd2z5X_1zeBjmOAnyj3iAANbsPA/view?usp=sharing) - recorded demo of the platform.

## Project Overview

MediBuddy was built as a cloud-based web platform for clinical simulation and diagnostic learning. The system uses a large language model to simulate structured patient interactions so that users can:

- take patient history in a conversational format,
- reason through signs and symptoms,
- form differential diagnoses,
- suggest investigations and treatment plans,
- receive feedback and scoring against reference clinical content.

The project is positioned as an educational and simulation platform rather than a replacement for clinical judgment or real-world medical diagnosis.

## Problem It Addresses

The project documentation identifies a gap in existing medical learning tools: many platforms are either static, expensive, narrowly scoped, or do not support context-aware clinical reasoning. MediBuddy aims to close that gap with an interactive, AI-assisted environment that combines:

- clinical dialogue practice,
- case-based learning,
- diagnostic reasoning support,
- evaluation and feedback.

## Core Capabilities

MediBuddy includes the following capabilities:

- AI-powered clinical dialogue simulation
- Case-based patient scenarios
- Quiz and question-answer generation
- Semantic scoring of user questions and final diagnostic responses
- Admin workflow for adding and managing medical cases
- User authentication with role-based access
- Cloud deployment for web and API access

## User Roles

MediBuddy supports two primary user roles:

- Student: logs in to practice diagnosis through case-based interaction, asks clinical questions, submits diagnosis and management plans, and receives scoring/feedback.
- Admin: logs in with elevated access to add and manage medical cases, maintain case data, and configure student practice/testing content.

## System Architecture

The documented system architecture consists of the following layers:

- Frontend: React.js application with responsive UI, routing, and dashboard-style interaction flows
- Backend: FastAPI service handling chat, scoring, context management, authentication, and case operations
- Database: MongoDB for case data, sessions, user information, and stored interactions
- AI layer: LLaMA 3.1 Aloe model served through Hugging Face Inference Endpoints
- Evaluation layer: BERTScore-based semantic comparison for user assessment and feedback

At a high level, the workflow is:

1. The user interacts through the React frontend.
2. The frontend sends requests to the FastAPI backend.
3. The backend manages context, session state, and case data.
4. The AI model generates clinically framed responses.
5. Responses and user inputs are evaluated and logged.
6. Scores and feedback are returned to the user interface.

## Documented Technology Stack

- Frontend: React.js, Tailwind CSS, React Router DOM, React Icons
- Backend: FastAPI, Pydantic, Uvicorn, FastAPI CORS middleware
- Database: MongoDB
- AI/NLP: LLaMA 3.1 Aloe, Hugging Face Inference Endpoints, BERTScore, biomedical embeddings
- Authentication: JWT-based authentication and role handling
- Design: Figma
- Deployment: Netlify for frontend, Render for backend, Hugging Face for model hosting

## Dataset and Methodology Summary

The presentation describes an original dataset of clinical cases in doctor-patient format, later processed into structured fields such as:

- doctor dialogue,
- patient information,
- diagnosis,
- diagnosis plan,
- case description,
- disease category.

The report also describes iterative data preparation, prompt engineering, scoring logic, deployment, and controlled validation with doctors and medical students.

Prompt engineering techniques mentioned in the documentation include:

- injecting patient-specific context into prompts,
- using structured delimiters,
- applying few-shot patterns,
- constraining model behavior to reduce hallucinations.

## Documented API Surface

The report lists the following backend endpoints:

- `GET /Med_cases`
- `POST /`
- `POST /res`
- `POST /qa`
- `POST /quiz`
- `POST /clear_history`
- `POST /set_context`
- `POST /addcase`
- `POST /score`
- `POST /finalScore`
- `POST /compare`
- `POST /set_ques`
- `POST /clear_ques`

These endpoints support case retrieval, chat interaction, quiz generation, context control, scoring, and admin-side case management.

## Deployment and Validation

According to the report, MediBuddy was deployed as a distributed cloud application:

- Frontend hosted on Netlify
- Backend hosted on Render
- AI inference deployed through Hugging Face Inference Endpoints

Validation was carried out in multiple stages:

- developer-level functional testing,
- expert review by doctors,
- controlled user testing with medical students.

The documentation also states that model outputs and user responses were evaluated using NLP-based metrics including BLEU and BERTScore, along with qualitative expert feedback.

## Intended Audience

MediBuddy is intended for:

- medical students,
- junior healthcare professionals,
- educators exploring AI-assisted clinical simulation,
- institutions interested in integrating diagnostic training tools.

## Important Note

This is a public documentation repository. If you are looking for the implementation code, deployment secrets, or private infrastructure configuration, those assets are not included here.

MediBuddy is described in the project documents as an educational and simulation tool. It should not be treated as a substitute for licensed medical practice or professional clinical decision-making.

## Documents

- [Project Report](./FYP%20Report_Medibuddy.pdf)
- [Final Presentation](./Final%20Presentation.pdf)

## Acknowledgment

The project report credits collaboration and support from:

- NUST College of Electrical and Mechanical Engineering
- NUST School of Health Sciences
- RISETech
- the project supervisors Dr. Usman Akram and Dr. Asad Mansoor Khan
- the student development team
