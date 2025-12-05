Folder Descriptions (Detailed)
api/

This layer exposes the feature through HTTP endpoints.
It connects external clients to internal workflows without exposing business logic.
Handles validation, authentication, and error formatting before passing requests to workflows.

workflows/

Coordinates the entire analysis process.
Orchestrates agents, tools, and services in a controlled sequence.
Manages shared state, prompt loading, memory behavior, and multi step execution.
Ensures the analysis pipeline runs in a predictable and maintainable flow.

workflows/code_quality/

A dedicated workflow for this feature.
Includes state definitions, prompt files, and workflow logic specific to code quality analysis.
Each component in this folder focuses only on this workflow’s responsibility.

agents/

Contains intelligent units that perform specialized tasks.
Each agent follows a standard interface and can be discovered, configured, or extended easily.
This design supports adding new analysis agents without changing the workflow architecture.

tools/

Pure functions that handle technical tasks such as complexity metrics, pattern detection, or code parsing.
They contain no business logic and no external dependencies.
Designed to be easily testable, reusable, and side effect free.

services/

Handles external data operations.
Responsible for:

fetching previous analysis results

saving new metrics

retrieving team or project quality standards
Uses existing database clients and caching layers inherited from the platform.

common/

A centralized space for shared resources used across all layers.
Helps avoid duplication and ensures consistent behavior throughout the system.

common/configs/

Stores configuration settings for models, database connections, feature flags, and environment values.
Ensures the system can adapt across environments without modifying the codebase.

common/utils/

General purpose helper utilities used across agents, workflows, and services.
Examples include:

LLM client wrappers

database connection helpers

text or parsing utilities
These functions improve developer productivity by centralizing common tasks.

common/models/

Defines data shapes, typed schemas, and shared response models.
Ensures all layers communicate using reliable, structured data formats.
Reduces errors from mismatch or inconsistent types.

common/templates/

Contains formatting templates used to generate final reports or summaries.
Separates presentation from logic, making it easy to adjust output style without code changes
