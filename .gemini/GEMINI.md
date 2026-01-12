# Gemini CLI Context - Personal Notes

This project contains personal notes and follows a **GTD (Getting Things Done)** workflow.

## System Philosophy

*   **Inbox (`inbox.md`)**: The primary landing zone for rapid thoughts and active tasks.
*   **Journal (`journal/`)**: An immutable audit trail. Every major reorganization or processing event creates a snapshot here.
*   **The Processor**: A specialized workflow to categorize and migrate data from the Inbox to permanent storage.

## Directory Structure

*   `inbox.md`: Active workspace.
*   `journal/`: History and snapshots.
*   `.gemini/`: Agent configuration and skills.

## Workflows

### Processing the Inbox

The primary maintenance task is processing the inbox. This involves:
1.  **Snapshotting**: Copying `inbox.md` to `journal/YYYY-MM-DD_HHMM.md`.
2.  **Refactoring**: Identifying items in `inbox.md` that are reference notes (to be moved) vs. active tasks (to be kept).
3.  **Logging**: Recording where items were moved.

Refer to `.gemini/skills/process-inbox/SKILL.md` for the detailed protocol.

## Git Configuration

*   **Tracked**: `.gemini/` (Configuration and Skills)
*   **Ignored**: All notes content (`inbox.md`, `journal/`, etc.) to keep personal data private.

## Operational Rules

*   **Accessing Ignored Files**: Since note files are git-ignored for privacy, you **MUST** explicitly bypass ignore patterns when searching or listing them.
    *   For `glob` and `list_directory`: Set `respect_git_ignore` to `false`.
    *   For `search_file_content`: Set `no_ignore` to `true`.

## Available Skills

*   **process-inbox**: Activates the specialized agent for organizing the inbox.
