# Laravel AgentKit Demo

A demonstration repository showcasing Claude skills, Cursor commands, and other AI-powered development tools for Laravel applications.

## About

This repository serves as a companion to the article ["Compound Engineering for Laravel"](https://brudtkuhl.com/blog/compound-engineering-for-laravel/), demonstrating how AI tools can enhance Laravel development workflows.

## What's Included

### Claude Skills (`.claude/skills/`)
- **Release**: Skills for managing version releases and deployment
- **Review**: Skills for code review and quality assurance

### Cursor Commands (`.cursor/rules/`)
- **Laravel Boost**: Custom rules and guidelines for Laravel development with AI assistance
- **Release**: Automated PR review, approval, and release workflow for Laravel projects
- **Review**: Comprehensive code review, testing, cleanup, and Git workflow management

### Laravel Application
A fully functional Laravel application demonstrating best practices for AI-assisted development.

## What are Agents?

Agents are specialized AI assistants that can perform specific tasks autonomously. In this repository:

- **Claude Skills**: Custom AI capabilities that extend Claude's functionality for specific Laravel development tasks
- **Cursor Commands**: AI-powered code generation and refactoring tools integrated into your editor
- **Boost Tools**: Laravel-specific AI enhancements that follow Laravel conventions and best practices

## Why This Repository?

This repository demonstrates the power of "compound engineering" - combining multiple AI tools to create a superior development experience:

- **Accelerated Development**: AI tools handle repetitive tasks, allowing you to focus on business logic
- **Consistent Code Quality**: AI follows established patterns and Laravel conventions
- **Faster Learning**: See how AI tools work together in a real Laravel application
- **Best Practices**: Learn how to integrate AI tools effectively into your workflow

## Getting Started

1. Clone this repository
2. Install dependencies: `composer install && npm install`
3. Set up your environment: `cp .env.example .env`
4. Run migrations: `php artisan migrate`
5. Start the development server: `php artisan serve`

## How to Use It

### Using Claude Skills
1. Copy the skills from `.claude/skills/` to your Claude workspace
2. Use the skills by mentioning them in your prompts (e.g., "Use the release skill to create a new version")

### Using Cursor Commands
1. The rules in `.cursor/rules/` are automatically applied when using Cursor with this project
2. Cursor will follow the Laravel Boost guidelines for code generation and assistance
3. Use the `review` command for comprehensive code review, testing, and cleanup: `cursor review`
4. Use the `release` command to automate PR approval, merging, and release tagging: `cursor release`

### Exploring the Application
- Run tests: `php artisan test`
- Check code quality: `vendor/bin/pint --test`
- View routes: `php artisan route:list`
- Use Tinker for debugging: `php artisan tinker`

## Contributing

We welcome contributions to improve AI-assisted Laravel development! Here's how you can help:

### Adding New Skills
1. Create a new skill file in `.claude/skills/`
2. Follow the existing skill format and documentation
3. Test the skill thoroughly before submitting

### Improving Cursor Rules
1. Update rules in `.cursor/rules/`
2. Ensure they align with Laravel best practices
3. Test the changes across different scenarios

### Enhancing the Demo App
1. Follow Laravel conventions and the established patterns
2. Add tests for new functionality
3. Update documentation as needed

### Guidelines
- Use descriptive commit messages
- Ensure all tests pass before submitting
- Follow the existing code style (Laravel Pint)
- Document any new features or changes

## Learn More

Read the companion article: ["Compound Engineering for Laravel"](https://brudtkuhl.com/blog/compound-engineering-for-laravel/)

## License

This project is open-sourced software licensed under the [MIT license](https://opensource.org/licenses/MIT).
