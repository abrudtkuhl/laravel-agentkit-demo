# Laravel AgentKit Demo

A demonstration repository showcasing Claude skills, Cursor commands, and other AI-powered development tools for Laravel applications.

## About

This repository serves as a companion to the article ["Compound Engineering for Laravel"](https://brudtkuhl.com/blog/compound-engineering-for-laravel/), demonstrating how AI tools can enhance Laravel development workflows.

## What's Included

### Claude Skills (`.claude/skills/`)
- **Release**: Skills for managing version releases and deployment
- **Review**: Skills for code review and quality assurance

### Cursor Integration (`.cursor/rules/`)
- **Laravel Boost Rules**: Custom guidelines for Laravel development with AI assistance
- **Command Integration**: Cursor commands that invoke the underlying Claude skills
- **Release/Review Commands**: Convenient shortcuts to the release and review skills

### Laravel Application
A fully functional Laravel application demonstrating best practices for AI-assisted development.

## What are Agents?

Agents are specialized AI assistants that can perform specific tasks autonomously. In this repository:

- **Claude Skills**: Custom AI capabilities that work in Claude Code, Cursor, and Opencode for specific Laravel development tasks
- **Cursor Integration**: Editor integration providing convenient shortcuts to Claude skills
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

### Using Claude Skills (Recommended)
The skills in `.claude/skills/` provide context-efficient AI assistance that works in Claude Code, Cursor, and Opencode:

1. **Skills load progressively** - only metadata loads initially (~100 tokens) to avoid context bloat
2. **Direct skill usage**: `skill name="review"` or `skill name="release"`
3. **Context efficiency**: Full instructions load only when needed, preventing "max context, can't compact" errors
4. **Multi-environment support**: Same skills work across Claude Code, Cursor, and Opencode

### Using Cursor Integration
1. The rules in `.cursor/rules/` provide Laravel-specific guidance and command shortcuts
2. Cursor commands serve as convenient shortcuts to the underlying Claude skills:
   - `cursor review` - invokes the review skill for comprehensive code review, testing, and cleanup
   - `cursor release` - invokes the release skill for PR approval, merging, and release tagging
3. Full skill functionality is available regardless of which interface you use

### Choosing Your Interface
- **Use skills directly** for maximum context efficiency and cross-environment compatibility
- **Use Cursor commands** for integrated editor experience and shortcuts

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

### Improving Skills and Commands
1. **Skills** (`.claude/skills/`): Primary implementation with progressive disclosure for context efficiency
2. **Cursor integration** (`.cursor/rules/`): Editor shortcuts and rules that invoke underlying skills
3. Changes to skills should be reflected in Cursor commands when applicable
4. Test across Claude Code, Cursor, and Opencode environments

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
