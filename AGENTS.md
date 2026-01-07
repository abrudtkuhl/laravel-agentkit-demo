# Agent Guidelines for Laravel AgentKit Demo

This repository contains AI-powered Laravel development tools. All agents must follow these guidelines for consistent, high-quality code.

## 🚀 Development Workflow Skills

For detailed build, testing, and quality assurance workflows, use the dedicated skills:

- **build**: Project setup, testing, and quality assurance (`skill name="build"` or `cursor build`)
- **lint**: Code quality and style validation (`skill name="lint"` or `cursor lint`)
- **style**: Laravel patterns and best practices (`skill name="style"` or `cursor style`)



## 🤖 AI Agent Guidelines

### Laravel Boost Integration & Skills
- Laravel Boost is an MCP server that comes with powerful tools designed specifically for this application. Use them.
- Use the `search-docs` tool for version-specific Laravel documentation before implementing features
- Use `list-artisan-commands` to verify available parameters for Artisan commands
- Use `get-absolute-url` tool to generate proper URLs for sharing with users
- Use skills for complex workflows that combine multiple tools and steps
- Skills complement MCP servers by providing contextual instructions without context bloat

### Project Evolution & Changelog
- **CHANGELOG.md** documents significant changes, new skills, and workflow updates
- **Check [Unreleased] section** for upcoming changes that may affect your work
- **Review recent entries** to understand new capabilities and why certain patterns exist
- **Reference when needed** to understand the evolution of tools and development approaches

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
| **build** | Project setup, testing, quality assurance | `skill name="build"` or `cursor build` | Project initialization, comprehensive testing, quality gates |
| **lint** | Code quality and style validation | `skill name="lint"` or `cursor lint` | Code formatting, naming conventions, type declarations |
| **style** | Laravel patterns and best practices | `skill name="style"` or `cursor style` | Framework compliance, security patterns, performance optimization |
| **review** | Code review, testing, cleanup, Git workflow | `skill name="review"` or `cursor review` | Comprehensive code quality checks, test execution, before commits |
| **release** | PR approval, merging, changelog, releases | `skill name="release"` or `cursor release` | Ready to merge approved PRs, deployment preparation |

### Available Skills

**build** - Project setup, testing, and quality assurance
- **Purpose**: Automated project initialization, testing pipeline, and code formatting
- **Location**: `.claude/skills/build/SKILL.md`
- **Usage**: `skill name="build"` or `cursor build`
- **When to Use**: Project setup, comprehensive testing, quality assurance before commits
- **Examples**:
  - Use for new project initialization
  - Use to run full test suite and formatting
  - Use before deployment to ensure quality gates pass
- **Key Features**: Environment setup, test execution, code formatting, CI/CD integration

**lint** - Code quality and style validation
- **Purpose**: Automated code quality checks and style enforcement
- **Location**: `.claude/skills/lint/SKILL.md`
- **Usage**: `skill name="lint"` or `cursor lint`
- **When to Use**: Code formatting, naming convention validation, type declaration checks
- **Examples**:
  - Use to validate PHP standards compliance
  - Use to check naming conventions across codebase
  - Use as pre-commit quality gate
- **Key Features**: Style validation, naming checks, type declaration coverage, automatic fixes

**style** - Laravel patterns and best practices
- **Purpose**: Laravel-specific conventions and framework compliance validation
- **Location**: `.claude/skills/style/SKILL.md`
- **Usage**: `skill name="style"` or `cursor style`
- **When to Use**: Framework compliance checks, security pattern validation, performance optimization
- **Examples**:
  - Use to validate Laravel patterns and conventions
  - Use for security best practices assessment
  - Use to ensure "Laravel Way" compliance
- **Key Features**: Framework patterns, security validation, performance optimization, best practices

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




