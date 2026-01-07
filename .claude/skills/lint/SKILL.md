---
name: lint
description: Code quality and style validation for Laravel applications
allowed-tools: Read, Grep, Glob, Bash, Edit, Write
---

You are a specialized Claude Code or Opencode or other agent that supports skill. This skill handles code quality validation and style enforcement for Laravel applications.

## Core Functionality

### 1. Code Quality Standards

- **PHP Version**: 8.4.16 minimum requirement
- **Code Formatting**: Use `vendor/bin/pint --dirty` for consistent formatting
- **Indentation**: 4 spaces (no tabs)
- **Max Line Length**: 120 characters

### 2. Naming Conventions

- **Classes**: PascalCase (`UserController`, `ProductService`)
- **Methods**: camelCase (`getUserById()`, `createNewOrder()`)
- **Variables**: camelCase (`$userEmail`, `$orderTotal`)
- **Constants**: UPPER_SNAKE_CASE (`MAX_RETRY_ATTEMPTS`, `DEFAULT_TIMEOUT`)
- **Database**: snake_case (`user_profiles`, `order_items`)

### 3. Type Declarations and Documentation

- **Return Types**: Always declare return types for methods
- **Parameter Types**: Always type-hint parameters
- **PHPDoc**: Use for complex logic, prefer inline types for simple cases
- **Property Types**: Declare types for class properties

### 4. Code Quality Validation

- **Syntax Checking**: PHP syntax validation
- **Style Consistency**: Laravel Pint compliance
- **Import Organization**: Proper use statements and namespace declarations
- **Unused Code**: Remove unused imports and variables

### 5. Quality Gates

- **Pre-commit Hooks**: Automatic quality checks before commits
- **CI/CD Integration**: Quality validation in automated pipelines
- **Manual Checks**: On-demand quality assessment

## Task Approach

1. Analyze codebase for quality and style issues
2. Execute automated formatting and validation tools
3. Identify and report any quality violations
4. Apply automatic fixes where possible
5. Flag issues requiring manual intervention

## Quality Checklist

### PHP Standards Compliance
- [ ] Correct indentation (4 spaces)
- [ ] Line length under 120 characters
- [ ] Proper PHP version compatibility

### Naming Convention Compliance
- [ ] Classes use PascalCase
- [ ] Methods use camelCase
- [ ] Variables use camelCase
- [ ] Constants use UPPER_SNAKE_CASE

### Type Declaration Compliance
- [ ] All methods have return types
- [ ] All parameters have type hints
- [ ] Complex logic has PHPDoc documentation

### Code Quality Issues
- [ ] No syntax errors
- [ ] No unused imports
- [ ] Consistent formatting
- [ ] No debug statements (`dd()`, `var_dump()`)

## Integration with Other Skills

- **build skill**: Run lint checks as part of build pipeline
- **review skill**: Use lint results for comprehensive code review
- **style skill**: Complement with Laravel-specific pattern validation

## Success Criteria

- All automated formatting applied successfully
- No syntax errors detected
- Naming conventions followed consistently
- Type declarations complete and accurate

## Return Format

Provide detailed report including:
- Formatting status (applied/not applied)
- Quality violations found and resolved
- Naming convention compliance status
- Type declaration coverage
- Any manual fixes required
- Overall code quality score</content>
<parameter name="filePath">.claude/skills/lint/SKILL.md