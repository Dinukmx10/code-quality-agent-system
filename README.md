#Folder Descriptions
Entry Point

run_code_quality_analysis.py
The CLI interface for the system. It reads arguments, validates inputs, sets logging, and initiates the workflow.

API Layer (api/)

Provides HTTP endpoints for triggering code analysis.
Handles request validation, authentication, and error responses.

Workflow Layer (workflows/)

Coordinates the steps involved in code analysis.
Controls state, prompts, agent calls, and pipeline sequencing.

workflows/code_quality/

A specialized workflow for code quality analysis.
Includes logic, state management, and prompt templates.

Agent Layer (agents/)

Contains intelligent components that execute tasks such as quality analysis or complexity evaluation.
Each agent is modular and discoverable through the platform’s registry.

Tools Layer (tools/)

Pure computational utilities used by agents and workflows.
These functions stay small, testable, and reusable across the platform.

Services Layer (services/)

Handles external interactions like fetching historical metrics, saving results, or retrieving standards.
Uses database clients, caching layers, and query builders provided by the architecture.

Common Layer (common/)

Contains shared utilities and configuration modules.

configs/
Environment, model, and database configuration.

utils/
Reusable helpers such as LLM clients and database connectors.

models/
Typed schemas and shared data representations used across layers.

templates/
Formatting templates for creating final reports.
