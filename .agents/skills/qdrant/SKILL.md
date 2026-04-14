```markdown
# qdrant Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill teaches the development patterns and conventions used in the `qdrant` repository, which is primarily written in TypeScript and leverages Rust as its core framework. You'll learn about file naming, import/export styles, commit message habits, and how to structure and run tests. This guide also provides suggested commands for common workflows, making it easier to contribute and maintain code consistency.

## Coding Conventions

### File Naming
- **Convention:** PascalCase
- **Example:**  
  ```plaintext
  VectorStore.ts
  CollectionManager.ts
  ```

### Import Style
- **Convention:** Relative imports
- **Example:**  
  ```typescript
  import { VectorStore } from './VectorStore';
  import { CollectionManager } from '../managers/CollectionManager';
  ```

### Export Style
- **Convention:** Named exports
- **Example:**  
  ```typescript
  export const createCollection = () => { /* ... */ };
  export function deleteCollection() { /* ... */ }
  ```

### Commit Patterns
- **Type:** Freeform (no enforced prefixes)
- **Average Length:** ~55 characters
- **Example:**  
  ```
  Add support for new vector similarity metric
  Fix bug in collection deletion logic
  ```

## Workflows

### Adding a New Feature
**Trigger:** When you need to implement a new feature.
**Command:** `/add-feature`

1. Create a new file using PascalCase (e.g., `NewFeature.ts`).
2. Use relative imports to include dependencies.
3. Export your feature using named exports.
4. Write corresponding tests in a `.test.ts` file.
5. Commit with a descriptive message (~55 chars).

### Fixing a Bug
**Trigger:** When you need to fix a bug.
**Command:** `/fix-bug`

1. Locate the relevant file(s) using PascalCase naming.
2. Apply the fix, maintaining code style and import/export conventions.
3. Update or add tests in a `.test.ts` file to cover the bug.
4. Commit with a clear, descriptive message.

### Writing and Running Tests
**Trigger:** When you need to ensure code correctness.
**Command:** `/run-tests`

1. Write test files using the pattern `*.test.ts`.
2. Place tests alongside or near the files they test.
3. Use the project's test runner (framework unknown; check project docs or package.json).
4. Run tests and ensure all pass before committing.

## Testing Patterns

- **Test File Pattern:** `*.test.ts`
- **Placement:** Tests are typically placed alongside implementation files.
- **Framework:** Not explicitly detected; check the repository for specifics.
- **Example:**
  ```typescript
  // VectorStore.test.ts
  import { VectorStore } from './VectorStore';

  describe('VectorStore', () => {
    it('should add a vector', () => {
      // test implementation
    });
  });
  ```

## Commands

| Command       | Purpose                                    |
|---------------|--------------------------------------------|
| /add-feature  | Start workflow for adding a new feature    |
| /fix-bug      | Start workflow for fixing a bug            |
| /run-tests    | Run all test suites                        |
```