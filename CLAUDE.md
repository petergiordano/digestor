# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Digestor** is an AI-powered newsletter processing system that ingests, summarizes, and presents newsletter content through an interactive layered exploration interface (the "Onion Reader" concept). The project follows SLC (Simple, Lovable, Complete) design principles and uses a 6-component pipeline architecture.

## Development Environment

### Setup
The project uses Python 3.8+ with a virtual environment:
```bash
source venv/bin/activate  # Automatically activated via Claude Code settings
pip install -r requirements.txt
```

### Key Dependencies
- **Email processing**: `imaplib2`, `email-validator`
- **Web scraping**: `requests`, `beautifulsoup4`, `lxml`
- **AI/ML**: `openai>=1.0.0`, `tiktoken`
- **Data processing**: `pandas`, `feedparser`

## Development Commands

### Testing
```bash
pytest tests/ -v                    # Run all tests
pytest tests/unit/ -v               # Unit tests only
pytest tests/integration/ -v        # Integration tests only
python scripts/test-framework.py    # Enhanced test runner with validation
```

### Code Quality
```bash
black src/                          # Format code
flake8 src/                         # Lint code
python scripts/validate-setup.py    # Validate project setup
```

### AI-Assisted Development
Use these Claude Code commands for structured development:
```bash
@orient                             # Get project status
@next-task                          # Select next component to work on
@finalize-task                      # Complete current work
@update-prd                         # Sync project status
@workflow-orchestrator              # Automate multi-step workflows
@production-readiness               # Check deployment readiness
@validate-all                       # Run comprehensive validation
```

## Architecture

### Component Pipeline
The system follows a 6-component sequential processing architecture:
1. **Input Handler** - Email/RSS ingestion
2. **Content Extractor** - Parse and clean content
3. **AI Processor** - Summarization and analysis
4. **Data Manager** - Storage and indexing
5. **UI Engine** - Interactive presentation layers
6. **Output Handler** - Export and sharing

### Directory Structure
- `src/utils/` - Core implementation (component modules go here)
- `tests/` - Multi-tier testing (unit/, integration/)
- `docs/specifications/` - PRD and feature specifications
- `.claude/` - AI coordination framework
- `config/` - Project configuration and templates
- `scripts/` - Automation and validation tools

### AI Development Framework
The project includes sophisticated AI coordination:
- **Steering System** (`.claude/steering/`) - Guidance for AI assistants on product, technical, and domain-specific aspects
- **Hooks Framework** (`.claude/hooks/`) - Event-driven automation for quality gates
- **Execution Modes** (`.claude/execution-modes/`) - Autopilot, supervised, and hybrid AI assistance levels
- **Validation Framework** (`scripts/validation/`) - Comprehensive quality assurance

## Development Workflow

1. **Spec-Driven Development**: Start with specifications in `docs/specifications/`
2. **Component-Based Implementation**: Build one component at a time in `src/utils/`
3. **AI-Assisted Coordination**: Use Claude Code commands to orchestrate development
4. **Quality Gates**: Automated validation and testing at each step

## Testing Strategy

The project uses an enhanced testing framework with:
- **Multi-format Reporting**: JSON, JUnit XML, HTML for CI/CD integration
- **Coverage Analysis**: XML coverage reports with configurable thresholds
- **Pre-test Validation**: Specifications, hooks, and production readiness checks
- **Integration with AI Framework**: Test results feed back into development coordination

## Key Configuration Files

- `pyproject.toml` - Build system and development tool configuration
- `config/project-config.json` - Project metadata and commands
- `.claude/gyro-config.json` - AI development framework settings
- `.claude/validation-config.json` - Quality assurance configuration
- `.claude/settings.local.json` - Local Claude Code settings (auto-activates venv)

## Project Focus Areas

- **Newsletter Processing**: Email integration, content extraction, AI-powered summarization
- **Interactive UI**: "Onion layers" concept for drilling down from summaries to full content
- **Multi-source Support**: Email, RSS feeds, manual uploads (planned)
- **Privacy-Focused**: End-to-end encryption and local processing options (planned)