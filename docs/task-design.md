> [中文版](task-design.zh-CN.md)

# Task Design Specification

A PABench task is a standardized scenario used to evaluate Personal AI Agents.

## Task Structure

Each task should define:

- Task ID
- Category
- Difficulty Level
- Objective
- User Persona
- Initial State
- Required Permissions
- Standard Operation Path
- Success Criteria
- Partial Success Criteria
- Failure Conditions
- Metrics
- Evidence Requirements

## Design Principles

### 1. Real-world scenarios

Tasks should represent meaningful user goals rather than artificial questions.

### 2. Clear execution paths

Each task must define the expected interaction flow while allowing natural agent behavior.

### 3. Verifiable outcomes

Results must have objective verification methods.

### 4. Measure effort, not only success

A task completed with excessive user guidance should receive different evaluation from an autonomous completion.

### 5. Separate evaluator-only and subject-visible content

Ground truth, answer keys, and labels such as "test" or "fictional" belong only in evaluator instructions. They must not appear in prompts, email bodies, calendar titles, or other content visible to the product under test. Use isolated test accounts and permissions for safety; do not rely on telling the product that it is being evaluated.

## Task Complexity Levels

### Level 1
Single-step assistance

### Level 2
Multi-step reasoning and planning

### Level 3
Tool usage and external actions

### Level 4
Cross-application workflows

### Level 5
Long-term autonomous assistance
