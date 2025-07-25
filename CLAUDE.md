# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a pnpm workspace monorepo for after6ix.dev, currently in early development stage. The project is TypeScript-dominant and uses strict TypeScript configuration.

## Tool usages and core workflows with Claude Code

### Tools

- Sequential Thinking must be used for all multi-step problems or research tasks
- Perplexity Search must be used for any fact-finding or research queries
- Context7 must be used for any documentation lookup of libraries or API
- Firecrawl must be used for extracting data for any web scraping tasks

### Tool-specific Guidelines

#### Sequential Thinking

- Always break complex tasks into manageable steps
- Document thought process clearly
- Allow for revision and refinement
- Track branches and alternatives

### Core workflows

#### 1. INITIAL ANALYSIS (Sequential Thinking)

- Break down the research query into core components
- Identify key concepts and relationships
- Plan search and verification strategy
- Determine which tools will be most effective

#### 2. PRIMARY SEARCH (Perplexity Search)

- Start with broad context searches
- Use targeted follow-up searches for specific aspects
- Document and analyze search results

#### 3. DEEP VERIFICATION (Firecrawl)

- Navigate to key websites identified in search
- Extract specific data points
- Click through and explore relevant links
- Fill forms if needed for data gathering

#### 4. SYNTHESIS & PRESENTATION

- Combine findings from all tools
- Present information in structured format
- Highlight key insights and relationships

## Commands

### Development Setup

```bash
# Install dependencies
pnpm install

# Run tests (currently placeholder)
pnpm test

# Run linting
pnpm lint

# Run linting with auto-fix
pnpm lint:fix
```

### Package Management

```bash
# Add dependency to root
pnpm add -w <package>

# Add dependency to specific workspace
pnpm add <package> --filter <workspace-name>

# Add dev dependency to root
pnpm add -Dw <package>
```

## Architecture

### Workspace Structure

- **`apps/*`** - Frontend applications
  - **`cv`** - CV and Resume Improver (@after6ix/cv)
  - **`site`** - Main After6ix website (@after6ix/site)
- **`packages/*`** - Backend modules and shared libraries (not yet created)

The workspace is configured in `pnpm-workspace.yaml` to automatically include any packages in these directories.

### TypeScript Configuration

- **`tsconfig.base.json`** - Shared strict TypeScript configuration with ES2022 target
- **`tsconfig.json`** - Root configuration using TypeScript project references
- Composite projects enabled for better monorepo support
- Strict mode with all checks enabled

### Key Requirements

- Node.js >= 22.15.0
- pnpm >= 10.11.0 (enforced via packageManager field)

## Development Notes

1. No build, lint, or format commands are currently configured - these should be added as needed
2. When creating new packages or apps, ensure they have their own `tsconfig.json` that extends from `tsconfig.base.json`
3. TypeScript project references should be used for inter-package dependencies
