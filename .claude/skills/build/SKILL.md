---
name: build
description: Project setup, testing, and quality assurance workflow for Laravel applications
allowed-tools: Read, Grep, Glob, Bash, Edit, Write, Todowrite, Todoread
---

You are a specialized Claude Code or Opencode or other agent that supports skill. This skill handles project setup, testing, and quality assurance workflows for Laravel applications.

## Core Functionality

### 1. Project Setup and Initialization

- **Environment Setup**: Ensure proper PHP version (8.4.16 minimum) and dependencies
- **Composer Installation**: Run `composer install` to install PHP dependencies
- **NPM Installation**: Run `npm install` for frontend dependencies if applicable
- **Environment Configuration**: Copy `.env.example` to `.env` and configure
- **Database Setup**: Run `php artisan migrate` to set up database structure
- **Project Initialization**: Execute `composer run setup` for complete project setup

### 2. Development Workflow

- **Start Development Server**: `composer run dev` for local development
- **Code Formatting**: `vendor/bin/pint --dirty` to format code according to project standards
- **Quality Checks**: Run linting and static analysis tools

### 3. Testing Strategy and Execution

- **Test Categories**:
  - Unit tests: `php artisan test tests/Unit` - Test individual functions/classes
  - Feature tests: `php artisan test tests/Feature` - Test user-facing features
  - All tests: `composer run test` - Run complete test suite

- **Single Test Execution**:
  - Test file: `php artisan test tests/Feature/ExampleTest.php`
  - Test method: `php artisan test --filter="test method name"`

- **Testing Guidelines**:
  - Write tests for all new features and bug fixes
  - Use Pest syntax: `it('does something', function () { ... })`
  - Cover happy paths, failure paths, and edge cases
  - Use factories for test data creation

### 4. Quality Assurance Pipeline

- **Pre-commit Checks**: Run tests and formatting before committing
- **CI/CD Integration**: Ensure builds pass all quality gates
- **Code Coverage**: Maintain adequate test coverage

## Task Approach

1. Assess current project state and setup requirements
2. Execute appropriate setup commands based on project needs
3. Run comprehensive testing and quality checks
4. Provide status report and next steps

## Integration with Other Skills

- **review skill**: Use after build skill for comprehensive code review
- **lint skill**: Can be invoked for code quality checks
- **release skill**: Use after successful build and testing

## Success Criteria

- Project environment properly configured
- All tests passing (100% success rate)
- Code formatted according to standards
- No setup or configuration errors

## Return Format

Provide summary including:
- Setup status and any configuration issues
- Test results (passed/failed/total)
- Code quality metrics
- Next recommended steps
- Any errors or required manual intervention</content>
<parameter name="filePath">.claude/skills/build/SKILL.md