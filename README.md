# Cursor MDC Rules - Enterprise-Grade Rule System

*Last updated: January 2025 - Major content improvements & YAML format fixes*

A comprehensive, performance-optimized collection of Cursor MDC rules following expert best practices for modern development workflows. This repository provides enterprise-level rule organization with 96% reduction in token usage and expert-recommended structure.

## 🚀 Key Improvements & Achievements

### Performance Optimizations
- **96% Token Reduction**: Converted large always-apply rules to smart auto-attachment (2,393 → 89 always-loaded lines)
- **Intelligent Loading**: Rules now load contextually based on file patterns and semantic triggers
- **Optimized Activation**: Improved glob patterns and activation strategies for better performance

### Expert-Level Organization
- **Numbered Hierarchy**: Implemented 000-999 prefix system for clear rule precedence
- **Flattened Structure**: Replaced deep nested directories with logical flat organization
- **Subject-Matter Grouping**: Organized by concern rather than technology stacks
- **Consistent Naming**: Standardized `<tool>-core-standards-auto.mdc` pattern

### Quality Improvements  
- **Universal YAML Frontmatter**: All files now have consistent, validated frontmatter with critical format compliance
- **Structured XML**: Reliable rule enforcement using XML instead of unreliable markdown lists
- **Comprehensive Coverage**: Production-ready rules across all major development areas
- **Complete Elixir Ecosystem**: Added comprehensive coverage for 9 major Elixir packages including authentication, caching, HTTP clients, and observability

## 🔧 Recent Major Updates & Fixes (January 2025)

### Critical YAML Frontmatter Format Fixes
Fixed **6 files** with malformed YAML frontmatter that had incorrect placement at bottom instead of required top position:
- **310-reflect-metadata-core-standards-auto.mdc** - TypeScript decorator metadata standards
- **311-tslib-core-standards-auto.mdc** - TypeScript runtime library helpers
- **312-jason-core-standards-auto.mdc** - Elixir JSON encoding/decoding
- **313-gettext-core-standards-auto.mdc** - Elixir internationalization
- **314-deep-merge-core-standards-auto.mdc** - Elixir data structure merging
- **412-lit-core-standards-auto.mdc** - Lit web components framework

**Impact**: These fixes ensure proper Cursor MDC rule activation and compliance with cursor-rules-creation standards.

### Major Content Improvements - Eliminated Placeholder Files
Completely rewrote **3 major placeholder files** from 82-line generic templates to comprehensive, production-ready standards:

#### 1. **MobX State Management (505-mobx-core-standards-auto.mdc)**
- **Expanded**: 82 lines → 200+ comprehensive lines
- **Added**: Complete TypeScript store implementation with `makeObservable`
- **Features**: Computed values, actions, async operations with `runInAction`
- **Integration**: React integration with observer components and mobx-react-lite
- **Testing**: Comprehensive patterns for observable, computed, and action testing
- **Production**: Strict mode configuration and performance optimization

#### 2. **Date-fns Utility Library (621-date-fns-core-standards-auto.mdc)**
- **Expanded**: 82 lines → 350+ comprehensive lines
- **Optimization**: Tree-shakable imports and bundle optimization strategies
- **Timezone**: Complete timezone handling with date-fns-tz integration
- **Operations**: Calendar operations, business day calculations, date range operations
- **Testing**: Time mocking, edge cases, leap year handling patterns
- **i18n**: Internationalization support with locale-specific formatting

#### 3. **XState State Machines (510-xstate-core-standards-auto.mdc)**
- **Expanded**: 82 lines → 400+ comprehensive lines
- **Implementation**: Complete TypeScript state machine with hierarchical states, guards, actions, services
- **React**: Integration with @xstate/react hooks and proper component patterns
- **DevTools**: Visualization and debugging setup with inspector tools
- **Testing**: Comprehensive coverage for state transitions, guards, actions, services, edge cases
- **Production**: Performance optimization and error handling strategies

### Additional Format & Quality Fixes
- **Fixed empty description** in `202-git-workflow.mdc` for proper YAML frontmatter compliance
- **Corrected malformed globs array** in `502-prisma-typescript-rules-auto.mdc` for proper pattern matching
- **Standardized YAML format** consistency across all rule files

### Quality Standards Applied
Each rewritten file now includes:
- **Real-world examples** from official documentation and community best practices
- **Complete TypeScript integration** with proper type definitions and interfaces
- **Comprehensive error handling** patterns and production-ready configurations
- **Testing strategies** covering unit tests, integration tests, and edge cases
- **Performance optimization** techniques and bundle size considerations
- **Production deployment** patterns following expert community standards

### Remaining Improvement Opportunities
Identified **11+ placeholder files** still requiring comprehensive content updates:
- File manipulation utilities (file-saver, hotkeys-js, jszip)
- Data processing libraries (lodash, slashes, uuid, csv2json, fast-csv)
- Additional testing and development tools

**Technical Compliance**: All updated files now properly follow cursor-rules-creation format with YAML frontmatter at top, proper glob patterns, non-negotiable vs requirement classifications, comprehensive correct/incorrect examples, and authoritative documentation references.

## 📁 Directory Structure

The new numbered system provides clear precedence and logical organization:

```
.cursor/rules/
├── 000-core/                    # Always-apply rules (3 files)
│   ├── 001-project-development-guidelines.mdc
│   ├── 002-cursor-rules-creation.mdc  
│   └── 003-code-review-standards.mdc
├── 100-security/                # Security rules (1 file)
│   └── 101-security-coding-standards.mdc
├── 200-quality/                 # Code quality & process (4 files)
│   ├── 201-git-workflow.mdc
│   ├── 202-eslint-core-standards-auto.mdc
│   ├── 203-husky-core-standards-auto.mdc
│   └── 204-lint-staged-core-standards-auto.mdc
├── 300-languages/               # Language-specific rules (12 files)
│   ├── 301-python-core-standards-auto.mdc
│   ├── 302-python-core-project-rules.mdc
│   ├── 303-python-testing-conventions-auto.mdc
│   ├── 304-typescript-core-standards-auto.mdc
│   ├── 305-typescript-monorepo-core-project-rules-auto.mdc
│   ├── 306-typescript-testing-conventions-auto.mdc
│   ├── 307-elixir-conventions-auto.mdc
│   ├── 308-elixir-core-project-rules-auto.mdc
│   ├── 309-elixir-testing-conventions-auto.mdc
│   ├── 312-jason-core-standards-auto.mdc
│   ├── 313-gettext-core-standards-auto.mdc
│   └── 314-deep-merge-core-standards-auto.mdc
├── 400-frameworks/              # Framework rules (4 files)
│   ├── 401-react-core-standards-auto.mdc
│   ├── 402-next.js-core-standards-auto.mdc
│   ├── 403-tailwind-core-standards-auto.mdc
│   └── 414-bandit-core-standards-auto.mdc
├── 500-architecture/            # Database & architecture (20 files)
│   ├── 501-postgresql.mdc
│   ├── 502-postgresql_security_rules.mdc
│   ├── 503-prisma-typescript-rules-auto.mdc
│   ├── 504-sqlite-python-rules-auto.mdc
│   ├── 505-mobx-core-standards-auto.mdc
│   ├── 506-sqlite-typescript-rules-auto.mdc
│   ├── 507-sqlalchemy-python-rules-auto.mdc
│   ├── 508-alembic-python-rules-auto.mdc
│   ├── 510-xstate-core-standards-auto.mdc
│   ├── 513-telemetry-metrics-core-standards-auto.mdc
│   ├── 514-telemetry-poller-core-standards-auto.mdc
│   ├── 515-cachex-core-standards-auto.mdc
│   ├── 516-goth-core-standards-auto.mdc
│   ├── 517-docker-core-standards-auto.mdc
│   ├── 518-kubernetes-core-standards-auto.mdc
│   ├── 519-kafka-core-standards-auto.mdc
│   ├── 520-redis-core-standards-auto.mdc
│   ├── 521-zookeeper-core-standards-auto.mdc
│   ├── 522-ory-core-standards-auto.mdc
│   └── 523-kratos-core-standards-auto.mdc
└── 600-tooling/                 # Build tools & utilities (24 files)
    ├── 601-npm-core-standards-auto.mdc
    ├── 602-yarn-core-standards-auto.mdc
    ├── 603-npx-core-standards-auto.mdc
    ├── 604-nx-core-standards-auto.mdc
    ├── 605-lerna-core-standards-auto.mdc
    ├── 606-vite-core-standards-auto.mdc
    ├── 607-tsx-core-standards-auto.mdc
    ├── 608-vitest-core-standards-auto.mdc
    ├── 609-playwright-core-standards-auto.mdc
    ├── 610-cypress-core-standards-auto.mdc
    ├── 611-console-clear-core-standards-auto.mdc
    ├── 612-chalk-core-standards-auto.mdc
    ├── 613-dotenv-core-standards-auto.mdc
    ├── 614-minimist-core-standards-auto.mdc
    ├── 615-shelljs-core-standards-auto.mdc
    ├── 616-readdirp-core-standards-auto.mdc
    ├── 617-ink-core-standards-auto.mdc
    ├── 618-mack-core-standards-auto.mdc
    ├── 619-json-schema-to-typescript-core-standards-auto.mdc
    ├── 620-md-to-pdf-core-standards-auto.mdc
    ├── 621-date-fns-core-standards-auto.mdc
    ├── 634-req-core-standards-auto.mdc
    ├── 635-kafka-ui-core-standards-auto.mdc
    └── 636-langgraph-core-standards-auto.mdc
```

## 🎯 New Elixir Ecosystem Coverage

### Recently Added Comprehensive Elixir Package Rules

**Language Utilities (300-languages/):**
- **Jason (312)** - JSON encoding/decoding with performance optimization, custom encoders, and comprehensive error handling
- **Gettext (313)** - Internationalization and localization with message extraction, pluralization, and context handling  
- **DeepMerge (314)** - Advanced data structure merging with conflict resolution, custom strategies, and performance optimization

**HTTP Server Framework (400-frameworks/):**
- **Bandit (414)** - Modern HTTP server with HTTP/2 support, security configuration, performance monitoring, and production deployment patterns

**Architecture & Observability (500-architecture/):**
- **TelemetryMetrics (513)** - Comprehensive observability with metrics collection, aggregation, SLA monitoring, and alerting integration
- **TelemetryPoller (514)** - Periodic measurements, system monitoring, custom pollers, and performance optimization
- **Cachex (515)** - Advanced caching with TTL management, performance optimization, monitoring, and distributed caching patterns
- **Goth (516)** - Google Cloud authentication with OAuth2, service accounts, token management, and security best practices
- **Docker (517)** - Containerization platform with multi-stage builds, security scanning, orchestration, and production deployment patterns
- **Kubernetes (518)** - Container orchestration with secure deployments, RBAC, monitoring integration, and advanced deployment strategies
- **Kafka (519)** - Message broker and streaming platform with cluster configuration, security, producer/consumer patterns, and monitoring
- **Redis (520)** - In-memory data store and cache with cluster configuration, high availability, advanced patterns, and real-time features
- **ZooKeeper (521)** - Distributed coordination service with ensemble configuration, security, distributed patterns, and monitoring
- **Ory (522)** - Complete identity and access management stack with OAuth2/OIDC, zero-trust architecture, and compliance measures
- **Kratos (523)** - Identity management with self-service flows, multi-factor authentication, progressive profiling, and session management

**HTTP Client Tooling (600-tooling/):**
- **Req (634)** - Modern HTTP client with middleware pipeline, authentication, comprehensive error handling, and performance monitoring
- **Kafka UI (635)** - Comprehensive Kafka management interfaces with cluster monitoring, security configuration, and operational dashboards
- **LangGraph (636)** - AI agent workflows with graph-based reasoning, state management, tool integration, and production monitoring

### Elixir Ecosystem Benefits

The new Elixir rules provide:
- **Complete Development Stack**: From HTTP servers to clients, authentication to caching
- **Production-Ready Patterns**: Enterprise-grade configurations with monitoring and security
- **Performance Optimization**: Advanced caching, connection pooling, and efficiency patterns
- **Observability Integration**: Comprehensive telemetry, metrics, and monitoring setup
- **Security Best Practices**: Authentication, token management, and secure communication patterns

## 🏗️ Infrastructure & Platform Coverage

### Recently Added Comprehensive Infrastructure Rules

**Containerization & Orchestration (500-architecture/):**
- **Docker (517)** - Production containerization with multi-stage builds, security scanning, performance optimization, and comprehensive orchestration patterns
- **Kubernetes (518)** - Enterprise container orchestration with secure deployments, RBAC, Pod Security Standards, advanced deployment strategies, and monitoring integration

**Message Streaming & Coordination (500-architecture/):**
- **Kafka (519)** - Production message broker with SSL/TLS security, producer/consumer patterns, topic design, Schema Registry integration, and monitoring
- **ZooKeeper (521)** - Distributed coordination with ensemble configuration, security, leader election, distributed locks, and performance tuning

**Data Storage & Caching (500-architecture/):**
- **Redis (520)** - High-performance in-memory store with cluster configuration, high availability, advanced caching strategies, and real-time features

**Identity & Access Management (500-architecture/):**
- **Ory (522)** - Complete identity stack deployment with Kratos/Hydra/Oathkeeper/Keto, OAuth2/OIDC, zero-trust architecture, and compliance measures
- **Kratos (523)** - User identity management with self-service flows, multi-factor authentication, session management, and progressive profiling

**Management & AI Tools (600-tooling/):**
- **Kafka UI (635)** - Kafka cluster management with monitoring dashboards, security configuration, RBAC, and operational efficiency
- **LangGraph (636)** - AI agent development with graph-based reasoning, state management, tool integration, safety measures, and production monitoring

### Infrastructure Benefits

The comprehensive infrastructure rules provide:
- **Cloud-Native Architecture**: Complete containerization and orchestration strategies
- **Distributed Systems**: Message streaming, coordination, and distributed data patterns
- **Security First**: Authentication, authorization, zero-trust, and comprehensive security measures
- **Enterprise Scale**: High availability, monitoring, alerting, and production-ready configurations
- **AI Integration**: Modern AI agent development with safety, monitoring, and cost optimization
- **Operational Excellence**: Management interfaces, monitoring dashboards, and operational efficiency

## 🎯 Usage Instructions

### Automatic Rule Loading

The system automatically loads relevant rules based on your context:

1. **Always-Apply Rules** (000-core): Load globally for all projects
2. **Auto-Attach Rules** (100-600): Load automatically based on file patterns and semantic triggers
3. **Manual Reference**: Some rules are available for explicit reference when needed

### File Pattern Matching

Rules automatically activate when working with relevant files:

```yaml
# Example: TypeScript rules activate for .ts/.tsx files
globs: ["**/*.{ts,tsx}"]

# Example: Testing rules activate for test files  
globs: ["**/*.{test,spec}.{js,ts,jsx,tsx}"]

# Example: Database rules activate for migration/schema files
globs: ["**/migrations/**/*", "**/schema.sql", "**/models/**/*"]
```

### Semantic Triggers

Many rules include semantic descriptions for contextual loading:

```yaml
description: "USE WHEN writing React components with TypeScript"
description: "USE WHEN setting up testing frameworks and writing tests"  
description: "USE WHEN working with database queries and migrations"
```

## 📝 Creating New Rules

### Best Practices for Rule Creation

#### 1. File Naming Convention
Use the standardized pattern: `<number>-<tool>-core-standards-auto.mdc`

```Examples:
✅ 621-jest-core-standards-auto.mdc
✅ 315-go-core-standards-auto.mdc  
✅ 415-vue-core-standards-auto.mdc
✅ 635-credo-core-standards-auto.mdc

❌ jest-rules.mdc
❌ go-best-practices.mdc
❌ vue_standards.mdc
```

#### 2. Directory Placement

Choose the appropriate numbered directory:

- **000-core**: Only for project-wide, always-apply rules
- **100-security**: Security-specific rules
- **200-quality**: Code quality, linting, git workflow  
- **300-languages**: Programming language specific rules (Python, TypeScript, Elixir utilities)
- **400-frameworks**: Web frameworks, UI libraries, HTTP servers
- **500-architecture**: Databases, ORM, containerization, orchestration, message streaming, caching, identity management, observability
- **600-tooling**: Build tools, testing frameworks, HTTP clients, management interfaces, AI development, development utilities

#### 3. Numbering System

Use the next available number in the chosen directory:

```bash
# Check existing numbers in target directory
ls -la .cursor/rules/600-tooling/

# Use next sequential number (e.g., if 634 exists, use 635)
635-new-tool-core-standards-auto.mdc
```

### Example: Adding Elixir Package Rules

The Elixir ecosystem rules follow the systematic approach:

```
# Language utilities go in 300-languages/
312-jason-core-standards-auto.mdc      # JSON library
313-gettext-core-standards-auto.mdc    # i18n/l10n
314-deep-merge-core-standards-auto.mdc # Data merging

# HTTP servers go in 400-frameworks/
414-bandit-core-standards-auto.mdc     # HTTP server

# Architecture components go in 500-architecture/
513-telemetry-metrics-core-standards-auto.mdc  # Metrics
514-telemetry-poller-core-standards-auto.mdc   # Monitoring
515-cachex-core-standards-auto.mdc             # Caching
516-goth-core-standards-auto.mdc               # Authentication
517-docker-core-standards-auto.mdc             # Containerization
518-kubernetes-core-standards-auto.mdc         # Orchestration
519-kafka-core-standards-auto.mdc              # Message streaming
520-redis-core-standards-auto.mdc              # In-memory store
521-zookeeper-core-standards-auto.mdc          # Distributed coordination
522-ory-core-standards-auto.mdc                # Identity stack
523-kratos-core-standards-auto.mdc             # Identity management

# Management and AI tools go in 600-tooling/
634-req-core-standards-auto.mdc        # HTTP client
635-kafka-ui-core-standards-auto.mdc   # Kafka management
636-langgraph-core-standards-auto.mdc  # AI agent development
```

### Prompt for Generating New Rules

Use this prompt template to generate new rules:

```
Create a comprehensive MDC cursor rule file for [TOOL/FRAMEWORK NAME] following the cursor-rules-creation standards from 002-cursor-rules-creation.mdc.

Requirements:
- File name: [NUMBER]-[tool]-core-standards-auto.mdc  
- Location: .cursor/rules/[APPROPRIATE-DIRECTORY]/
- Include YAML frontmatter at the very top with description, globs array, and alwaysApply: false
- Use structured XML format with <rule>, <meta>, <requirements>, <examples>
- Include both correct-example and incorrect-example for each requirement
- Cover [SPECIFIC AREAS like setup, configuration, best practices, common patterns]
- Include expert best practices and modern patterns
- Add comprehensive examples with TypeScript integration
- Follow the numbered prefix system for the target directory

Generate a production-ready rule file with 300-500 lines covering:
1. [SPECIFIC REQUIREMENT 1]
2. [SPECIFIC REQUIREMENT 2]  
3. [SPECIFIC REQUIREMENT 3]
4. [etc.]
```

**Example for creating a new Jest rule:**

```
Create a comprehensive MDC cursor rule file for Jest testing framework following the cursor-rules-creation standards from 002-cursor-rules-creation.mdc.

Requirements:
- File name: 635-jest-core-standards-auto.mdc
- Location: .cursor/rules/600-tooling/
- Include YAML frontmatter at the very top with description, globs array, and alwaysApply: false
- Use structured XML format with <rule>, <meta>, <requirements>, <examples>
- Include both correct-example and incorrect-example for each requirement
- Cover Jest configuration, test organization, mocking patterns, coverage
- Include expert best practices and modern Jest patterns
- Add comprehensive examples with TypeScript integration
- Follow the numbered prefix system for 600-tooling directory

Generate a production-ready rule file with 300-500 lines covering:
1. Jest configuration with TypeScript
2. Test file organization and naming
3. Modern testing patterns (describe/it/test)
4. Mocking strategies and best practices
5. Coverage configuration and thresholds
6. Integration with CI/CD pipelines
```

## 🎨 Prompt Engineering for Code Generation

### Using Rules in Development Prompts

#### Basic Pattern
```
Generate [SPECIFIC CODE/FEATURE] following the [RELEVANT RULE NAME] standards.

[SPECIFIC REQUIREMENTS]

Ensure compliance with:
- [RULE 1]: [SPECIFIC ASPECT]
- [RULE 2]: [SPECIFIC ASPECT]
- [RULE 3]: [SPECIFIC ASPECT]
```

#### Comprehensive Example: React Component with Testing

```
Create a React user profile component with comprehensive TypeScript testing following these standards:

Requirements:
- Component: UserProfile that displays user info with edit functionality
- Props: user object with id, name, email, avatar fields
- Features: Display mode, edit mode toggle, form validation, save/cancel
- State management using useState for edit mode and form data

Ensure compliance with:
- react-core-standards-auto: Functional components, proper hooks usage, TypeScript props
- typescript-core-standards-auto: Strict typing, interfaces, proper exports
- typescript-testing-conventions-auto: Comprehensive test coverage, React Testing Library
- vitest-core-standards-auto: Modern test configuration, coverage thresholds
- tailwind-core-standards-auto: Utility-first styling, responsive design

Generate:
1. UserProfile.tsx component with full TypeScript support
2. UserProfile.types.ts for type definitions  
3. UserProfile.test.tsx with comprehensive test suite
4. UserProfile.stories.tsx for Storybook (if applicable)

Include:
- Component implementation with all required features
- Full test coverage including user interactions, form validation, edge cases
- Proper TypeScript interfaces and type safety
- Modern React patterns and hooks
- Accessible markup and interactions
- Responsive Tailwind CSS styling
```

#### Database Development Example

```
Create a SQLAlchemy user model and Alembic migration following database best practices:

Requirements:
- User model with authentication fields (id, email, password_hash, created_at, updated_at)
- Email uniqueness constraint and proper indexing
- Password hashing integration
- Proper relationship setup for future user profiles
- Migration script for initial table creation

Ensure compliance with:
- sqlalchemy-python-rules-auto: Modern SQLAlchemy 2.0 patterns, type hints, model structure
- alembic-python-rules-auto: Migration best practices, rollback support, proper naming
- python-core-standards-auto: PEP compliance, type hints, proper imports
- postgresql: Database-specific optimizations and constraints

Generate:
1. User model class with all fields and relationships
2. Alembic migration script for table creation
3. Unit tests for model validation and constraints
4. Repository pattern implementation for user operations

Include:
- SQLAlchemy 2.0 syntax with proper type hints
- Database indexes for performance optimization
- Proper constraint definitions and validation
- Migration with both upgrade and downgrade paths
- Comprehensive test coverage for all model methods
```

#### API Development Example

```
Create a FastAPI user authentication endpoint with comprehensive testing:

Requirements:
- POST /auth/login endpoint for user authentication
- JWT token generation and validation
- Request/response models with validation
- Error handling for invalid credentials
- Rate limiting and security headers

Ensure compliance with:
- python-core-standards-auto: PEP compliance, type hints, async patterns
- python-testing-conventions-auto: Pytest patterns, async testing, mocking
- security-coding-standards: Secure authentication, input validation, SQL injection prevention
- postgresql: Secure database queries, proper connection handling

Generate:
1. FastAPI router with authentication endpoints
2. Pydantic models for request/response validation
3. JWT utilities for token generation/validation
4. Comprehensive test suite with pytest
5. Security middleware and rate limiting

Include:
- Async/await patterns throughout
- Proper error handling and HTTP status codes
- Security best practices for password handling
- Comprehensive test coverage including security edge cases
- Database integration with proper connection management
```

### Rule-Specific Prompts

#### For Frontend Development
```
Build a [COMPONENT/FEATURE] using:
- React functional components with hooks
- TypeScript for full type safety
- Tailwind CSS for styling
- Vitest for testing
- Modern accessibility patterns

Following: react-core-standards-auto, typescript-core-standards-auto, tailwind-core-standards-auto, vitest-core-standards-auto
```

#### For Backend Development
```
Implement [API/SERVICE] using:
- Python with FastAPI/Django
- SQLAlchemy for ORM
- Alembic for migrations
- Pytest for testing
- PostgreSQL database

Following: python-core-standards-auto, sqlalchemy-python-rules-auto, alembic-python-rules-auto, postgresql
```

#### For Testing Workflows
```
Create comprehensive test suite for [FEATURE] including:
- Unit tests with high coverage
- Integration tests for API endpoints
- E2E tests for user workflows
- Performance and security testing

Following: [language]-testing-conventions-auto, [testing-framework]-core-standards-auto
```

### Elixir Development Workflow

With the comprehensive Elixir ecosystem rules, you can now generate complete Elixir applications:

#### Full-Stack Elixir Web Application

```
Create a complete Elixir Phoenix application with the following components:
- User authentication with Google OAuth
- Real-time features with LiveView
- Caching layer for performance
- Comprehensive observability
- API endpoints with proper HTTP handling
- Internationalization support

Ensure compliance with:
- elixir-conventions-auto: Modern Elixir patterns, GenServer usage, OTP principles
- elixir-core-project-rules-auto: Project structure, dependency management, configuration
- bandit-core-standards-auto: HTTP server with security and performance optimization
- goth-core-standards-auto: Secure Google authentication with token management
- cachex-core-standards-auto: Intelligent caching with TTL and performance monitoring
- telemetry-metrics-core-standards-auto: Comprehensive observability and SLA monitoring
- jason-core-standards-auto: Efficient JSON handling with custom encoders
- gettext-core-standards-auto: Proper internationalization and localization
- req-core-standards-auto: Robust HTTP client for external API integration

Generate:
1. Phoenix application structure with proper supervision tree
2. User authentication module with Google OAuth integration
3. LiveView components for real-time user interface
4. Caching layer with Cachex for performance optimization
5. Telemetry setup for monitoring and observability
6. HTTP client module for external service integration
7. Comprehensive test suite covering all components
8. Internationalization setup with multiple language support
```

#### Elixir Microservices Architecture

```
Design a microservices-based Elixir system with:
- HTTP API service with Bandit server
- Background job processing service
- Shared caching layer with Cachex
- Centralized observability with TelemetryMetrics
- Service-to-service communication with Req
- Data synchronization and merging with DeepMerge

Following the complete Elixir ecosystem rules for:
- Proper OTP application structure
- Secure authentication and authorization
- Performance-optimized HTTP handling
- Comprehensive monitoring and alerting
- Efficient caching strategies
- Robust error handling and retry mechanisms
```

#### Elixir Library Development

```
Create a production-ready Elixir library with:
- Comprehensive API design following Elixir conventions
- JSON serialization with Jason
- HTTP client capabilities with Req
- Built-in caching with Cachex
- Observability hooks with TelemetryMetrics
- Deep configuration merging with DeepMerge
- Internationalization support with Gettext

Include:
- Complete hex package setup with proper versioning
- Comprehensive ExUnit test suite with property-based testing
- Documentation with ExDoc and usage examples
- CI/CD pipeline with quality checks and performance benchmarks
- Integration examples for common use cases
```

## 🛠 Advanced Usage

### Rule Precedence

The numbered system determines loading order:
1. **000-core**: Always loaded first
2. **100-600**: Loaded based on context and file patterns
3. **Within directories**: Lower numbers take precedence

### Custom Activation

For specialized workflows, rules can be activated manually:

```
Following the [specific-rule-name] standards, create...
```

### Debugging Rule Loading

Add this to any prompt to verify rule activation:

```
Before generating code, confirm which MDC rules are currently active and list the key requirements being followed.
```

## 📚 Additional Resources

- [Cursor MDC Documentation](https://docs.cursor.com/rules)
- [Rule Format Examples](.cursor/rules/000-core/002-cursor-rules-creation.mdc)
- [Expert Best Practices Research](https://docs.cursor.com/chat/rules)

---

*This enterprise-grade rule system represents months of optimization and expert research. The 96% token reduction and expert organization patterns make it suitable for large-scale development teams and complex codebases.*
