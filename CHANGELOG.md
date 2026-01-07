# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

### Added
- New build skill: Project setup, testing, and quality assurance workflow
- New lint skill: Code quality and style validation for PHP/Laravel standards
- New style skill: Laravel-specific patterns and best practices guidance

### Changed
- Updated AGENTS.md to reference Claude Code skills system for context efficiency
- Replaced brief Cursor Commands section with comprehensive Skills System documentation
- Added skills quick reference table and usage guidelines to prevent context bloat
- Consolidated duplicate Laravel Boost Integration sections and added skills references
- Refactored build/test/lint commands and code style guidelines into modular skills
- Reduced AGENTS.md token count by ~30 lines through progressive disclosure
- Updated README.md to emphasize skills-first approach while maintaining Cursor command examples
- Added context efficiency benefits and multi-environment support (Claude Code, Cursor, Opencode)

## [1.2.0] - 2025-01-15

### Changed
- Synced Claude skills from chatseo repository
- Enhanced release skill with changelog update functionality
- Updated Cursor release command to match Claude skill improvements
- Release workflow now commits changelog updates to PR before merging

## [1.1.0] - 2025-01-15

### Added
- Cursor commands that mirror Claude skills functionality
- `review.mdc`: Comprehensive code review command for Laravel projects
- `release.mdc`: Automated PR review, approval, and release command
- Updated README.md with Cursor command usage instructions
- Improved AGENTS.md with comprehensive agent guidelines (build/lint/test commands, code style, Laravel ecosystem rules)

## [1.0.1] - 2025-01-15

### Changed
- Updated README.md with comprehensive documentation
- Added "What are Agents?" section explaining AI tools
- Added "Why This Repository?" section describing compound engineering benefits
- Added "How to Use It" section with practical instructions
- Added "Contributing" section with contribution guidelines

## [1.0.0] - 2025-01-15

### Added
- Initial Laravel application with AI agent integration
- Claude skills for release management and code review (`.claude/skills/`)
- Cursor commands and rules for Laravel development (`.cursor/rules/`)
- Laravel Boost integration for enhanced AI assistance
- CHANGELOG.md for tracking project changes
- Comprehensive README with setup and usage instructions</content>
<parameter name="filePath">/Users/andybrudtkuhl/Sites/laravel-agentkit-demo/CHANGELOG.md