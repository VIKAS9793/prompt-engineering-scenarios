# Troubleshooting Guide

Common issues when using AI coding prompts and how to solve them.

## 🚨 AI Output Quality Issues

### Problem: AI generates overly complex code for prototypes
**Symptoms:**
- Simple prototype takes days to implement
- AI suggests enterprise patterns for demo code
- Focus shifts to architecture over functionality

**Solutions:**
1. Emphasize speed constraints: "This must be working in 4 hours"
2. Explicitly allow shortcuts: "Hardcoded values are acceptable for this demo"
3. Limit refinement cycles: "One refinement cycle maximum"
4. Provide examples: "Like a hackathon project, not production code"

**Prompt Modifications:**
```
SPEED CONSTRAINT: This must be demonstrable within [timeframe].
Prioritize working functionality over code quality. Shortcuts and technical debt are explicitly acceptable.
```

### Problem: AI generates too simple code for production
**Symptoms:**
- Missing error handling for edge cases
- No security considerations
- Basic code that won't handle real-world load

**Solutions:**
1. Stress production context: "This will handle real money/data"
2. Add specific requirements: "Must handle 10,000 concurrent users"
3. Include failure scenarios: "What happens if the database is down?"
4. Demand security review: "Include OWASP Top 10 considerations"

**Prompt Modifications:**
```
PRODUCTION CONTEXT: This system will handle [specific scale/criticality].
Assume hostile environment with unreliable dependencies. Include comprehensive error handling.
```

### Problem: AI doesn't follow the verification checklist
**Symptoms:**
- AI skips verification steps
- Produces code that fails its own checklist
- Doesn't explain reasoning

**Solutions:**
1. Make verification mandatory: "Do not proceed without completing verification"
2. Request explicit checking: "Go through each checklist item and confirm"
3. Ask for reasoning: "Explain why each verification item passes or fails"

**Prompt Modifications:**
```
MANDATORY: Before providing final code, explicitly check each verification
item and state PASS/FAIL with reasoning. If any item fails, refine the code.
```

## 🎯 Scenario Selection Issues

### Problem: Choosing between two scenarios
**Common Conflicts:**
- Prototype vs. MVP: "Need it fast but users will see it"
- MVP vs. Enterprise: "Real users but not mission-critical yet"
- Startup vs. MVP: "Limited resources but need quality"

**Resolution Strategy:**
1. Identify your biggest risk:
   - Time pressure → Choose faster option
   - User experience → Choose quality option
   - Business risk → Choose safer option
2. Consider evolution path:
   - Start with simpler prompt
   - Plan explicit upgrade milestone
   - Document what you're deferring
3. Hybrid approach: Combine elements from both prompts

### Problem: Project doesn't fit any scenario
**Common Situations:**
- Modernizing legacy system while maintaining uptime
- Building internal tools with some compliance needs
- Research project that needs to be production-ready

**Solutions:**
1. Break project into phases: Use different prompts for different phases
2. Combine prompts: Take verification items from multiple scenarios
3. Customize existing prompt: Start with closest match and adapt

## ⚙️ Technical Implementation Issues

### Problem: AI suggests technologies your team doesn't know
**Symptoms:**
- Recommendations for unfamiliar frameworks
- Architectural patterns your team hasn't used
- Dependencies that create operational overhead

**Solutions:**
1. Specify technology constraints: "Use only React, Node.js, and PostgreSQL"
2. Include team context: "Team has 2 years Python experience, new to Go"
3. Request alternatives: "Provide solution using familiar technologies"

**Prompt Modifications:**
```
TECHNOLOGY CONSTRAINTS: Team expertise limited to [list technologies].
Avoid suggesting new frameworks or patterns. Use mainstream, well-documented approaches.
```

### Problem: Solutions don't fit your infrastructure
**Symptoms:**
- Cloud-native solutions when you're on-premises
- Microservices when you need monolith
- Database choices that don't match your setup

**Solutions:**
1. Specify infrastructure constraints: "Must work on single Ubuntu server"
2. Include deployment context: "Kubernetes cluster" or "Traditional VPS"
3. Mention existing systems: "Must integrate with existing MySQL database"

### Problem: AI ignores performance requirements
**Symptoms:**
- Solutions that won't scale to required load
- No consideration of latency requirements
- Memory-intensive approaches for resource-constrained environments

**Solutions:**
1. Quantify requirements: "Must handle 1000 requests/second with <200ms response time"
2. Specify constraints: "Limited to 512MB RAM, single CPU core"
3. Include benchmarking: "Include performance testing approach"

**Prompt Modifications:**
```
PERFORMANCE REQUIREMENTS: [specific metrics].
Include performance considerations in architecture decisions and verification checklist.
```

## 🔄 Process Issues

### Problem: Too many refinement cycles
**Symptoms:**
- AI keeps refining without meaningful improvement
- Stuck in analysis paralysis
- Diminishing returns on iterations

**Solutions:**
1. Set hard limits: "Maximum 3 refinement cycles"
2. Define "good enough": "Passes 80% of verification items is acceptable"
3. Time-box iterations: "Each refinement cycle maximum 1 hour"

### Problem: Skipping important steps
**Symptoms:**
- AI jumps straight to code without architecture
- Missing constraint analysis
- No edge case consideration

**Solutions:**
1. Enforce step completion: "Do not proceed to next step until current step is complete"
2. Request explicit outputs: "Show me the architecture plan before coding"
3. Break into separate requests: Ask for planning first, then implementation

## 🏗️ Architecture Issues

### Problem: Over-engineered solutions
**Symptoms:**
- Complex patterns for simple problems
- Multiple abstraction layers for straightforward logic
- Infrastructure overkill for current needs

**Solutions:**
1. Emphasize simplicity: "Start with simplest solution that works"
2. Constrain scope: "Single file solution preferred"
3. Question complexity: "Justify any abstraction layer"

### Problem: Under-engineered solutions
**Symptoms:**
- No separation of concerns
- Hardcoded business logic
- No extensibility for known future requirements

**Solutions:**
1. Specify growth plans: "Must accommodate 3 more similar features"
2. Include maintenance considerations: "Code will be maintained by different developers"
3. Request flexibility points: "Where would this need to change for different requirements?"

## 🔐 Security Issues

### Problem: AI ignores security requirements
**Symptoms:**
- No input validation
- Secrets in code
- Missing authentication/authorization

**Solutions:**
1. Make security explicit: "Include security as primary concern"
2. Specify threat model: "Assume hostile internet environment"
3. Reference standards: "Follow OWASP Top 10 guidelines"

### Problem: Over-securing prototypes
**Symptoms:**
- Complex authentication for internal demos
- Enterprise security patterns for proof-of-concepts
- Security slowing down validation

**Solutions:**
1. Define security scope: "Basic input validation only for prototype"
2. Defer complex security: "Document security requirements for next phase"
3. Use development patterns: "Development authentication acceptable"

## 🧪 Testing Issues

### Problem: No testing strategy in AI output
**Symptoms:**
- Code without any tests
- No consideration of testability
- Missing validation approaches

**Solutions:**
1. Include testing in verification: Add testing requirements to checklist
2. Specify testing approach: "Include unit tests for core logic"
3. Request test scenarios: "Provide test cases that validate requirements"

### Problem: Over-testing for rapid phases
**Symptoms:**
- Comprehensive test suites for prototypes
- Testing slowing down iteration speed
- More test code than actual code

**Solutions:**
1. Scope testing appropriately: "Basic smoke tests only for prototype"
2. Focus on critical paths: "Test only the main user journey"
3. Defer comprehensive testing: "Document testing strategy for next phase"

## 🚀 Deployment Issues

### Problem: Complex deployment for simple projects
**Symptoms:**
- Kubernetes configs for single-server apps
- CI/CD pipelines for prototypes
- Over-engineered infrastructure

**Solutions:**
1. Specify deployment context: "Single server deployment via SSH"
2. Limit infrastructure scope: "No containers or orchestration"
3. Request simple deployment: "Must deploy with single command"

### Problem: No deployment consideration
**Symptoms:**
- Code that only works in development
- Missing production configuration
- No deployment documentation

**Solutions:**
1. Include deployment in requirements: "Must be deployable to production"
2. Specify target environment: "AWS EC2, Ubuntu 20.04"
3. Request deployment guide: "Include step-by-step deployment instructions"

## 🔧 Quick Fixes Reference

**Common Prompt Additions**

For speed:
```
TIMELINE CONSTRAINT: Must be complete within [timeframe]. 
Prioritize working functionality over perfection.
```

For quality:
```
QUALITY REQUIREMENT: This will be maintained long-term by multiple developers. 
Prioritize clarity and maintainability.
```

For scale:
```
SCALE REQUIREMENT: Must handle [specific numbers] users/requests. 
Design for this scale from the beginning.
```

For team context:
```
TEAM CONTEXT: [size] developers with [experience level] in [technologies]. 
Solutions must match team capabilities.
```

For infrastructure:
```
INFRASTRUCTURE CONTEXT: Deployment target is [specific environment]. 
All solutions must work within these constraints.
```

## 📞 When to Ask for Help

**Escalate to Community When:**
- Multiple prompt attempts yield unsatisfactory results
- Scenario seems missing from available options
- AI consistently misunderstands your requirements
- Technical constraints are too specific for generic prompts

**Create an Issue When:**
- Prompt contains errors or ambiguities
- Verification checklist items are unclear
- Process steps don't flow logically
- Documentation is missing or incorrect

**Contribute Improvements When:**
- You find solutions to common problems
- You develop better prompt variations
- You have real-world examples to share
- You identify missing scenarios
