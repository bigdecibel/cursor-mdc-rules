# Cursor Rules Guidelines for Engineers

*Last updated: January 2025*

After extensive testing and community research, here's what I've learned about writing effective Cursor rules that actually work in production.

## TL;DR

Use **YAML frontmatter + structured XML** for reliable rule enforcement. Simple markdown lists are unreliable and get ignored by AI models. The structured approach works consistently across different models and complex codebases.

## The Reality of Rule Processing

Cursor processes rules in two phases:

1. **Frontmatter parsing** - Determines when rules load
2. **Content interpretation** - Raw text passed to AI model

The AI doesn't "understand" your markdown bullets. It needs structure to follow instructions consistently.

## Rule Format Comparison

### What Doesn't Work Reliably

```yaml
---
description: Next.js best practices
globs: "app/**/*.*"
---
- Use server components by default
- Implement client components only when necessary
- Use App Router for routing
```

**Problems I've encountered:**
- AI ignores rules mid-conversation
- No priority hierarchy
- Ambiguous requirements
- No enforcement mechanism

### What Actually Works

```yaml
---
description: "Rules for Next.js best practices"
globs: "*.{js,jsx,ts,tsx}"
alwaysApply: false
---

<rule>
  <meta>
    <title>Next.js Best Practices</title>
    <description>Comprehensive Next.js development patterns</description>
    <created-at utc-timestamp="1744157700">January 25, 2025, 10:15 AM</created-at>
    <applies-to>
      <file-matcher glob="*.{js,jsx,ts,tsx}">Next.js files</file-matcher>
    </applies-to>
  </meta>
  <requirements>
    <non-negotiable priority="critical">
      <description>Use App Router for all new routing implementations</description>
      <examples>
        <example title="App Router Implementation">
          <correct-example title="Proper App Router usage" conditions="Creating new routes" expected-result="App Router structure" correctness-criteria="Uses app/ directory structure">
// app/dashboard/page.tsx
export default function Dashboard() {
  return <div>Dashboard</div>;
}
          </correct-example>
          <incorrect-example title="Legacy Pages Router" conditions="Creating new routes" expected-result="App Router structure" incorrectness-criteria="Uses pages/ directory">
// pages/dashboard.tsx - DON'T DO THIS
export default function Dashboard() {
  return <div>Dashboard</div>;
}
          </incorrect-example>
        </example>
      </examples>
    </non-negotiable>
  </requirements>
  <references>
    <reference as="dependency" href=".cursor/rules/rules.mdc" reason="Follows standard rule format">Base rule format definition</reference>
  </references>
</rule>
```

**Why this works better:**
- **Explicit priorities** - `critical`, `high`, `medium`, `low`
- **Concrete examples** - Shows exactly what to do/avoid
- **Enforcement levels** - `requirement` vs `non-negotiable`
- **Dependency tracking** - Rules reference each other
- **Consistent parsing** - AI models handle XML structure reliably

## Frontmatter Configuration

The frontmatter controls **when** rules are loaded:

### Always Apply (Global Rules)
```yaml
---
description: "Project-wide development guidelines"
globs: "*"
alwaysApply: true
---
```
Use for: Core standards, security requirements, global patterns

### File Pattern Matching
```yaml
---
description: "React component patterns"
globs: "*.{jsx,tsx}"
alwaysApply: false
---
```
Use for: Technology-specific rules, framework patterns

### Semantic Selection
```yaml
---
description: "USE WHEN writing or debugging database queries"
globs: ""
alwaysApply: false
---
```
Use for: Task-specific rules, specialized workflows

### Manual Reference Only
```yaml
---
description: ""
globs: ""
alwaysApply: false
---
```
Use for: Templates, complex workflows referenced by other rules

## Engineering Best Practices

### Rule Priority Hierarchy

```xml
<non-negotiable priority="critical">
  <!-- Security, data integrity, breaking changes -->
</non-negotiable>

<requirement priority="high">
  <!-- Performance, maintainability, team standards -->
</requirement>

<requirement priority="medium">
  <!-- Code style, documentation, nice-to-haves -->
</requirement>
```

### Example Structure That Works

I use this template for consistent rule creation:

```xml
<requirement priority="high">
  <description>Single, specific, measurable requirement</description>
  <examples>
    <example title="Descriptive Example Name">
      <correct-example title="What good looks like" conditions="When this applies" expected-result="What should happen" correctness-criteria="How to verify it's correct">
        // Actual code example
      </correct-example>
      <incorrect-example title="What to avoid" conditions="Same conditions" expected-result="Same expected result" incorrectness-criteria="Why this is wrong">
        // Actual bad code example
      </incorrect-example>
    </example>
  </examples>
</requirement>
```

### Dependency Management

Always reference the base rule format:

```xml
<references>
  <reference as="dependency" href=".cursor/rules/rules.mdc" reason="Follows standard rule format">Base rule format definition</reference>
</references>
```

For related rules:
```xml
<reference as="context" href=".cursor/rules/typescript.mdc" reason="TypeScript patterns">TypeScript standards</reference>
<reference as="examples" href=".cursor/rules/react.mdc" reason="Component examples">React patterns</reference>
```

## Common Anti-Patterns I've Seen

### ❌ Vague Requirements
```xml
<description>Write good code</description>
<!-- AI has no idea what this means -->
```

### ✅ Specific Requirements  
```xml
<description>Maximum function length is 30 lines excluding comments and whitespace</description>
<!-- AI can enforce this -->
```

### ❌ Multiple Concepts in One Rule
```xml
<description>Use TypeScript interfaces and handle errors properly and write tests</description>
<!-- Three different concerns -->
```

### ✅ Single Responsibility
```xml
<description>Define TypeScript interfaces for all component props</description>
<!-- One clear requirement -->
```

## Debugging Rules

### Check Rule Loading
Add temporary debug rules to verify loading:

```yaml
---
description: "Debug rule to verify loading"
globs: "*"
alwaysApply: true
---

<rule>
  <requirements>
    <requirement priority="low">
      <description>Confirm this rule is loaded by mentioning "Rule system active" in responses</description>
    </requirement>
  </requirements>
</rule>
```

### Validate Rule Selection
Start new chat sessions to test rule loading (rules are loaded at chat start, not dynamically).

### Use Editor Association Fix
If you can't edit .mdc files properly, add to settings:

```json
{
  "workbench.editorAssociations": {
    "*.mdc": "default"
  }
}
```

## What I've Learned From Production Use

1. **Start simple, iterate** - Begin with basic rules, add complexity as needed
2. **Test frequently** - Rules behave differently across AI models
3. **Be specific** - Vague rules get ignored under pressure
4. **Use examples** - Concrete code examples are worth 1000 words of description
5. **Monitor effectiveness** - Rules that don't get followed need revision

## Current Status (January 2025)

The Cursor team is still evolving the rules system. From their community forum:
- Both formats "can work well"
- Official guidance coming soon
- Community consensus favors structured approach for complex projects

For production systems, I recommend the structured XML approach. It's more verbose but significantly more reliable than markdown lists.

## Migration Strategy

If you have existing markdown rules:

1. **Keep them working** - Don't break what works
2. **Gradually migrate** - Convert rules as you update them  
3. **Test thoroughly** - Verify behavior doesn't change
4. **Document decisions** - Note why you chose specific approaches

The investment in structured rules pays off as your codebase and team grow.

---

*This document reflects real-world usage patterns as of January 2025. The rules system is evolving rapidly, so these practices may need updates.*
