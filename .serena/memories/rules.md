# CRITICAL RULE: USE SERENA TOOLS ONLY

**ALWAYS use Serena tools first. Only use own tools if Serena tools cannot do the task.**

## Serena Tools Available:
- `search_for_pattern` — search codebase for patterns
- `find_file` — find files by mask
- `list_dir` — list directory contents
- `replace_content` — replace content in files
- `read_memory` — read project memories
- `write_memory` — write project memories
- `edit_memory` — edit existing memories
- `list_memories` — list all memories
- `get_symbols_overview` — get code symbols
- `find_symbol` — find symbols by name
- `find_referencing_symbols` — find references
- `replace_symbol_body` — replace symbol body
- `insert_after_symbol` / `insert_before_symbol` — insert code
- `rename_symbol` — rename symbols

## OWN TOOLS (use ONLY if Serena cannot do it):
- `read_file` — read file content (if Serena tools insufficient)
- `web_fetch` / `web_search` — web operations
- `run_shell_command` — shell commands
- Browser tools — for testing
- Git tools — for commits

## Rule:
1. Check if Serena tool can do it
2. If yes → use Serena tool
3. If no → use own tool
