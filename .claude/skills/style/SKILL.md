---
name: style
description: Laravel-specific patterns and best practices guidance
allowed-tools: Read, Grep, Glob, Edit, Write
---

You are a specialized Claude Code or Opencode or other agent that supports skill. This skill provides Laravel-specific patterns, conventions, and best practices guidance.

## Core Functionality

### 1. Laravel Pattern Compliance

#### Models
- **Property Casting**: Use `casts()` method instead of `$casts` property
- **Relationships**: Define proper Eloquent relationships with return type hints
- **Mass Assignment**: Define `$fillable` or `$guarded` for security
- **Accessors/Mutators**: Use proper naming conventions

#### Controllers
- **Thin Controllers**: Keep controllers thin, delegate to services/models
- **Form Requests**: Use Form Request classes for validation instead of inline validation
- **Resource Classes**: Use API Resource classes for consistent JSON responses
- **Dependency Injection**: Inject dependencies through constructor or methods

#### Routes
- **Named Routes**: Use named routes for maintainable URL generation
- **Route Model Binding**: Leverage implicit and explicit route model binding
- **Route Groups**: Organize routes with appropriate middleware groups
- **Resource Routes**: Use resourceful routing where applicable

#### Validation
- **Form Requests**: Always use Form Request classes for complex validation
- **Custom Rules**: Create custom validation rules for business logic
- **Validation Messages**: Provide user-friendly validation messages

#### Security
- **Authorization**: Use Gates and Policies for access control
- **Mass Assignment Protection**: Proper use of `$fillable`/`$guarded`
- **Input Sanitization**: Validate and sanitize all user inputs
- **CSRF Protection**: Ensure CSRF tokens are properly handled

### 2. Laravel Ecosystem Rules

#### "Do Things the Laravel Way"
- **Artisan Commands**: Use `php artisan make:` commands for consistent file generation
- **No Interaction Flag**: Always pass `--no-interaction` to Artisan commands
- **Eloquent Relationships**: Prefer Eloquent over raw SQL queries
- **Query Optimization**: Use eager loading to prevent N+1 query problems
- **Service Layer**: Extract business logic into service classes when appropriate

#### Testing Standards
- **Pest Framework**: All tests must use Pest syntax
- **Test Structure**: Tests live in `tests/Feature` and `tests/Unit` directories
- **Test Coverage**: Cover happy paths, failure paths, and edge cases
- **Factory Usage**: Use factories for consistent test data creation

#### Code Quality
- **Laravel Pint**: Always run `vendor/bin/pint --dirty` before finalizing changes
- **Debug Cleanup**: Remove `dd()`, `var_dump()`, `console.log()` before committing
- **Documentation**: Update README.md and CHANGELOG.md for significant changes

### 3. Pattern Validation and Suggestions

- **Code Analysis**: Scan for Laravel anti-patterns and violations
- **Best Practice Recommendations**: Suggest Laravel-appropriate solutions
- **Framework Compliance**: Ensure code follows Laravel conventions
- **Performance Patterns**: Identify potential performance issues

## Task Approach

1. Analyze codebase for Laravel pattern compliance
2. Identify violations of Laravel best practices
3. Provide specific recommendations for improvement
4. Suggest Laravel-appropriate alternatives to non-idiomatic code

## Laravel Pattern Checklist

### Model Patterns
- [ ] Uses `casts()` method instead of `$casts` property
- [ ] Has proper relationship definitions with return types
- [ ] Defines mass assignment protection
- [ ] Follows Laravel naming conventions

### Controller Patterns
- [ ] Delegates business logic appropriately
- [ ] Uses Form Requests for validation
- [ ] Returns consistent response formats
- [ ] Avoids being overly complex

### Route Patterns
- [ ] Uses named routes
- [ ] Leverages route model binding
- [ ] Applies appropriate middleware
- [ ] Follows RESTful conventions

### Security Patterns
- [ ] Uses Gates/Policies for authorization
- [ ] Protects against mass assignment
- [ ] Validates all user inputs
- [ ] Handles CSRF protection

## Integration with Other Skills

- **build skill**: Validate Laravel patterns during build process
- **lint skill**: Complement with general code quality checks
- **review skill**: Include Laravel pattern validation in comprehensive review

## Success Criteria

- Code follows Laravel conventions and best practices
- No anti-patterns detected
- Security measures properly implemented
- Performance patterns optimized

## Return Format

Provide comprehensive assessment including:
- Laravel pattern compliance status
- Specific violations found and recommendations
- Security assessment results
- Performance optimization suggestions
- Code improvement recommendations</content>
<parameter name="filePath">.claude/skills/style/SKILL.md