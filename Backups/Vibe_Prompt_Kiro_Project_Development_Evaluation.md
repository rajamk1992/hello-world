# Project Development Evaluation

## Vibe Coding vs Prompt Coding vs Kiro Approach

------------------------------------------------------------------------

## 1. Vibe Coding

### Overview

Vibe coding is an informal development style where developers use AI
tools to quickly generate applications by describing high-level ideas
instead of detailed technical specifications.

### How It Works

-   Developer gives high-level idea
-   AI generates code
-   Developer iterates and refines
-   Rapid experimentation

### Advantages

-   Very fast prototyping
-   Ideal for MVP development
-   Encourages creativity

### Risks

-   Weak architecture design
-   Security vulnerabilities
-   Increased technical debt
-   Difficult to scale

### Best Use Cases

-   Hackathons
-   Startup MVPs
-   Internal tools
-   Early product validation

------------------------------------------------------------------------

## 2. Prompt Coding

### Overview

Prompt coding is a structured method of generating code using detailed
and technically clear AI prompts.

### Example

Instead of: "Build a banking API"

Use: "Build a REST API using Node.js, Express, JWT authentication,
role-based access, PostgreSQL, layered architecture, and proper error
handling."

### Characteristics

-   Structured prompt design
-   Clear technical constraints
-   Repeatable output
-   Architecture-focused

### Advantages

-   Better maintainability
-   Cleaner architecture
-   More control over output
-   Suitable for production systems

### Risks

-   Depends on prompt quality
-   Requires strong technical clarity
-   AI output still needs review

### Best Use Cases

-   FinTech systems
-   Enterprise APIs
-   Scalable SaaS platforms

------------------------------------------------------------------------

## 3. Kiro Approach

### Overview

Kiro represents a structured AI-assisted engineering workflow focused on
governance, quality control, and traceability.

### Focus Areas

-   Requirement clarity
-   Architecture alignment
-   Test-driven AI generation
-   Code review automation
-   CI/CD integration

### Advantages

-   Strong governance
-   Better documentation
-   Improved quality control
-   Enterprise-ready

### Best Use Cases

-   Banking systems
-   Regulated industries
-   Large enterprise applications
-   Multi-team development environments

------------------------------------------------------------------------

# Comparison Table

  Aspect                Vibe Coding   Prompt Coding     Kiro Approach
  --------------------- ------------- ----------------- --------------------
  Speed                 Very Fast     Fast              Moderate
  Structure             Low           Medium-High       High
  Governance            Low           Medium            High
  Scalability           Risky         Good              Strong
  Technical Debt Risk   High          Medium            Low
  Suitable For          MVP           Production APIs   Enterprise Systems

------------------------------------------------------------------------

# Project Manager Evaluation Checklist

When evaluating project development approach:

1.  Architecture clarity
2.  Security validation
3.  Code review process
4.  Test coverage
5.  AI dependency risk
6.  Long-term maintainability

------------------------------------------------------------------------

# Recommendation

-   Startup Projects → Vibe Coding → Refine using Prompt Coding
-   FinTech Projects → Prompt Coding + Governance
-   Banking / Enterprise Projects → Structured Kiro-style Approach
