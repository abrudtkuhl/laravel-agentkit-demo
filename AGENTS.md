# Agent Guidelines for Laravel AgentKit Demo

This repository contains AI-powered Laravel development tools. All agents must follow these guidelines for consistent, high-quality code.

## 🚀 Build, Lint & Test Commands

### Primary Commands
- **Setup project**: `composer run setup`
- **Start development**: `composer run dev`
- **Run all tests**: `composer run test`
- **Format code**: `vendor/bin/pint --dirty`

### Single Test Commands
- **Run test file**: `php artisan test tests/Feature/ExampleTest.php`
- **Run test method**: `php artisan test --filter="test method name"`
- **Run unit tests**: `php artisan test tests/Unit`
- **Run feature tests**: `php artisan test tests/Feature`

## 📝 Code Style Guidelines

### PHP Standards
- **PHP Version**: 8.4.16 minimum
- **Indentation**: 4 spaces (no tabs)
- **Max line length**: 120 characters

### Naming Conventions
- **Classes**: PascalCase (`UserController`)
- **Methods**: camelCase (`getUserById()`)
- **Variables**: camelCase (`$userEmail`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_RETRY_ATTEMPTS`)
- **Database**: snake_case (`user_profiles`)

### Type Declarations
- **Return types**: Always declare return types for methods
- **Parameter types**: Always type-hint parameters
- **PHPDoc**: Use for complex logic, prefer inline for simple

### Laravel Patterns
- **Models**: Use `casts()` method, not `$casts` property
- **Controllers**: Keep thin, use Form Requests and Resources
- **Routes**: Use named routes and route model binding
- **Validation**: Use Form Requests, not inline validation
- **Security**: Define `$fillable` or `$guarded`, use Gates/Policies

## 🤖 AI Agent Guidelines

### Laravel Boost Integration & Skills
- Laravel Boost is an MCP server that comes with powerful tools designed specifically for this application. Use them.
- Use the `search-docs` tool for version-specific Laravel documentation before implementing features
- Use `list-artisan-commands` to verify available parameters for Artisan commands
- Use `get-absolute-url` tool to generate proper URLs for sharing with users
- Use skills for complex workflows that combine multiple tools and steps
- Skills complement MCP servers by providing contextual instructions without context bloat

### Debugging & Development
- Use the `tinker` tool for PHP code execution and debugging
- Use `database-query` tool for read-only database operations
- Use `browser-logs` tool to read recent browser logs and errors
- Use `last-error` tool to get details of the last backend error/exception

## 🎯 Skills System

To prevent context bloat while maintaining specialized functionality, this project uses Claude Code's skills system. Skills are stored in `.claude/skills/` and provide progressive disclosure - metadata loads first, full instructions only when invoked.

### Skills Directory Structure
```
.claude/skills/
├── review/
│   └── SKILL.md
└── release/
    └── SKILL.md
```

### Skills Quick Reference

| Skill | Purpose | Usage | When to Use |
|-------|---------|-------|-------------|
| **review** | Code review, testing, cleanup, Git workflow | `skill name="review"` or `cursor review` | Comprehensive code quality checks, test execution, before commits |
| **release** | PR approval, merging, changelog, releases | `skill name="release"` or `cursor release` | Ready to merge approved PRs, deployment preparation |

### Available Skills

**review** - Comprehensive code review, testing, cleanup, and Git workflow
- **Purpose**: Automated code quality assurance, test execution, debug cleanup, documentation updates
- **Location**: `.claude/skills/review/SKILL.md`
- **Usage**: `skill name="review"` or `cursor review`
- **When to Use**: Before committing changes, comprehensive code review needed, test failures to fix
- **Examples**:
  - Use for new feature development with tests
  - Use when multiple files changed and need validation
  - Use instead of manual `php artisan test` + manual review
- **Key Features**: Branch validation, code analysis, test execution/fixing, debug cleanup, changelog/PR updates

**release** - Automated PR review, approval, and release workflow
- **Purpose**: Streamlined PR approval, merging, changelog management, and deployment
- **Location**: `.claude/skills/release/SKILL.md`
- **Usage**: `skill name="release"` or `cursor release`
- **When to Use**: After review skill completion, ready to merge approved PRs
- **Examples**:
  - Use when PR is reviewed and tests pass
  - Use for production deployments with changelog updates
  - Use instead of manual PR merging + tagging
- **Key Features**: CI validation, changelog updates, PR approval/merging, Git tagging

### Skills Usage Guidelines
- **Progressive Loading**: Skills load metadata (~100 tokens) initially, full instructions on demand
- **Tool Permissions**: Each skill specifies allowed tools for security and focus
- **Workflow Integration**: Use `review` → `release` for complete development cycles
- **Context Efficiency**: Skills prevent main guidelines from exceeding token limits
- **Fallback**: For simple tasks, use direct commands instead of skills

### Skills vs Direct Commands
- **Use Skills**: Multi-step workflows, specialized domain tasks, complex validation
  - Examples: Full code review cycle, PR merge + release process
- **Use Direct**: Simple Git operations, quick file edits, standard Laravel commands
  - Examples: `git add .`, `php artisan make:model`, quick test run

## 🔧 Development Tools & Workflow

### Git Workflow
- Use descriptive commit messages following conventional commits format
- Create feature branches for new work: `git checkout -b feature/description`
- Run tests before committing: `composer run test`
- Format code before committing: `vendor/bin/pint --dirty`

### Testing Strategy
- Write tests for all new features and bug fixes
- Use Pest syntax: `it('does something', function () { ... })`
- Cover happy paths, failure paths, and edge cases
- Use factories for test data creation
- Run single tests with: `php artisan test --filter="test name"`

### Code Quality
- Always run `vendor/bin/pint --dirty` before finalizing changes
- Remove debug statements (`dd()`, `var_dump()`, `console.log()`) before committing
- Update documentation (README.md, CHANGELOG.md) for significant changes

## 📚 Laravel Ecosystem Rules

### Do Things the Laravel Way
- Use `php artisan make:` commands to create new files (migrations, controllers, models, etc.)
- Pass `--no-interaction` to all Artisan commands to ensure they work without user input
- Always use proper Eloquent relationship methods with return type hints
- Use Eloquent models and relationships before suggesting raw database queries
- Generate code that prevents N+1 query problems by using eager loading

### Testing
- All tests must be written using Pest: `php artisan make:test --pest {name}`
- Tests should test all happy paths, failure paths, and edge cases
- Tests live in `tests/Feature` and `tests/Unit` directories
- Use Pest syntax: `it('does something', function () { ... })`

### Code Quality
- You must run `vendor/bin/pint --dirty` before finalizing changes to ensure code matches project style
- Remove debug statements (`dd()`, `var_dump()`, `console.log()`) before committing
- Update documentation (README.md, CHANGELOG.md) for significant changes


