```markdown
# localsend Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches you the core development patterns and conventions used in the `localsend` Rust codebase. You'll learn how to structure files, write imports and exports, follow commit message conventions, and understand the project's approach to testing. This guide also provides suggested commands for common workflows to streamline your development process.

## Coding Conventions

### File Naming
- Use **snake_case** for all file names.
  - Example: `file_transfer.rs`, `network_utils.rs`

### Import Style
- Use **relative imports** within the codebase.
  - Example:
    ```rust
    use crate::utils::file_helper;
    use super::network;
    ```

### Export Style
- Use **named exports** for exposing functions, structs, or modules.
  - Example:
    ```rust
    pub fn send_file(...) { ... }
    pub struct TransferStatus { ... }
    ```

### Commit Messages
- Follow **conventional commit** style.
- Use prefixes like `fix` for bug fixes.
- Keep commit message length around 78 characters.
  - Example:
    ```
    fix: resolve panic when receiving empty file list
    ```

## Workflows

### Fix a Bug
**Trigger:** When you need to resolve a bug or issue in the codebase  
**Command:** `/fix-bug`

1. Identify the bug and locate the relevant code.
2. Create a new branch for your fix.
3. Apply the fix, following coding conventions.
4. Write or update tests as needed.
5. Commit your changes using the `fix:` prefix.
6. Open a pull request for review.

### Add a New Feature
**Trigger:** When implementing a new feature  
**Command:** `/add-feature`

1. Plan the feature and design the API.
2. Create a new branch for the feature.
3. Add new files using snake_case naming.
4. Use relative imports for internal modules.
5. Export new functionality using named exports.
6. Write tests for the new feature.
7. Commit with a descriptive message (e.g., `feat: add file encryption support`).
8. Open a pull request.

### Run Tests
**Trigger:** To verify code correctness after changes  
**Command:** `/run-tests`

1. Locate test files matching the `*.test.*` pattern.
2. Use the project's test runner (framework unknown; typically `cargo test` in Rust).
3. Review test output and address any failures.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern.
  - Example: `file_transfer.test.rs`
- Testing framework is not explicitly specified, but Rust projects commonly use the built-in test framework.
- Example test structure:
  ```rust
  #[cfg(test)]
  mod tests {
      use super::*;

      #[test]
      fn test_file_send() {
          // test logic here
      }
  }
  ```

## Commands
| Command      | Purpose                                   |
|--------------|-------------------------------------------|
| /fix-bug     | Start the bug fixing workflow             |
| /add-feature | Start the new feature implementation flow |
| /run-tests   | Run all tests in the codebase             |
```