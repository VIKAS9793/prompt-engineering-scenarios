# Frequently Asked Questions

## 🚀 Getting Started

### Q: Which AI models work best with these prompts?
**A:** These prompts are designed to work with most modern AI coding assistants:

**Recommended:**
- GPT-4 / GPT-4 Turbo (ChatGPT Plus/Pro)
- Claude 3.5 Sonnet / Claude 4 (Claude.ai Pro)
- GitHub Copilot Chat

**Works Well:**
- GPT-3.5-turbo (basic ChatGPT)
- Claude 3 Haiku
- Gemini Pro

**Best Results:** More capable models (GPT-4, Claude 4) generally produce better outputs with the enterprise-level prompts.

### Q: Can I modify these prompts for my specific needs?
**A:** Absolutely! These are templates meant to be adapted. Common modifications:
- Add domain-specific requirements: "Must comply with GDPR" or "Must work in Unity game engine"
- Adjust team context: "Team is experienced in Python but new to React"
- Modify verification criteria: Add or remove checklist items based on your priorities
- Change refinement limits: Adjust the number of allowed refinement cycles

### Q: How do I know if I'm using the right prompt?
**A:** Warning signs you might be using the wrong prompt:

**Too Heavy:**
- Spending days on a simple demo
- AI suggesting enterprise patterns for prototypes
- Focus shifting to architecture over functionality

**Too Light:**
- Production system lacking basic error handling
- Security concerns not addressed
- Code that won't handle real user load

**Just Right:**
- Development pace matches your timeline expectations
- AI suggestions align with your risk tolerance
- Output quality matches your current needs

## 🔄 Process Questions

### Q: What if the AI doesn't follow the verification checklist?
**A:** Try these approaches:
1. Make verification explicit: "Before providing code, check each item in the verification checklist and state PASS/FAIL"
2. Break into steps: Ask for architecture first, then code, then verification
3. Add enforcement: "Do not provide final code until all verification items pass"
4. Be specific: Instead of "secure code", say "include input validation and SQL injection prevention"

### Q: How many refinement cycles should I allow?
**A:** Depends on your scenario:
- **Rapid Prototyping:** 1 cycle maximum (speed is priority)
- **MVP Development:** 2-3 cycles (balance speed and quality)
- **Enterprise Production:** Unlimited until all checks pass (quality is priority)
- **Custom Rule:** Stop when diminishing returns set in

### Q: Should I use these prompts for every coding task?
**A:** No. These prompts are designed for substantial development work:

**Use These Prompts For:**
- New features or products
- System architecture decisions
- Complex problem-solving
- Code that others will maintain

**Don't Use For:**
- Simple bug fixes
- Minor tweaks to existing code
- Quick scripts or one-off tools
- Learning/educational exercises

## 🎯 Scenario Selection

### Q: My project doesn't fit any scenario exactly. What should I do?
**A:** You have several options:
1. Choose the closest match and adapt the verification checklist
2. Use a hybrid approach by combining elements from 2-3 scenarios
3. Start with MVP Development (most balanced) and adjust as needed
4. Create a custom prompt using our template in `/templates/`

### Q: Can I use different prompts for different parts of my project?
**A:** Yes! This is often the right approach:

**Example - E-commerce Platform:**
- **Payment processing:** Enterprise Production (critical reliability)
- **Product catalog:** MVP Development (needs user feedback)
- **Admin tools:** Rapid Prototyping (internal use only)
- **Analytics:** Research/Experimental (testing new approaches)

### Q: When should I switch from one prompt to another?
**A:** Common transition triggers:

**Prototype → MVP:**
- Demo successful, stakeholders want user version
- Need to show to actual users
- Reliability becomes important

**MVP → Enterprise:**
- Paying customers depend on uptime
- Security incidents would damage business
- Planning for 10x+ user growth

**Research → Prototype:**
- Hypothesis validated
- Ready to show proof of concept
- Commercial potential identified

## 🏗️ Technical Questions

### Q: The AI suggests technologies my team doesn't know. How do I fix this?
**A:** Add technology constraints to your prompt:
```
TECHNOLOGY CONSTRAINTS: Team expertise limited to [list your technologies].
Avoid suggesting new frameworks. Use mainstream, well-documented approaches with [your tech stack].
```

### Q: How do I handle conflicting requirements (like speed + quality)?
**A:** Several strategies:
- Prioritize by component: High quality for core features, speed for peripheral ones
- Time-box quality: "Spend max 2 days on optimization"
- Define "good enough": "80% of verification items passing is acceptable"
- Plan evolution: Start fast, plan upgrade milestones

### Q: What if my infrastructure constraints aren't addressed?
**A:** Add specific infrastructure context:
```
INFRASTRUCTURE CONSTRAINTS:
- Deployment: Single Ubuntu server, no containers
- Database: Existing MySQL 5.7, cannot change
- Integrations: Must work with legacy SOAP APIs
- Resources: 4GB RAM, 2 CPU cores maximum
```

## 🔐 Security & Compliance

### Q: How do I handle security requirements not covered in the prompts?
**A:** Add specific security requirements:
```
SECURITY REQUIREMENTS:
- Must comply with [specific standards like PCI-DSS, HIPAA]
- Authentication via [existing system/protocol]
- Encryption requirements: [specific algorithms/standards]
- Audit trail must track [specific events]
```

### Q: Can I use the compliance-heavy prompt for non-regulated industries?
**A:** Yes, if you need similar rigor:
- High-security applications
- Financial applications (even if not regulated)
- Applications handling sensitive personal data
- Systems where security breach would be catastrophic

Adapt the regulatory references to your specific security standards.

## 🧪 Troubleshooting

### Q: The AI output is too complex for my needs. How do I simplify?
**A:** Try these prompt modifications:
```
SIMPLICITY CONSTRAINT: Start with the simplest solution that works.
Justify any complexity. Prefer single-file solutions when possible.
```

**Add to Core Behaviors:**
- Avoid abstraction layers unless clearly necessary
- Use straightforward, obvious approaches
- Optimize for readability over cleverness

### Q: The AI output is too simple for production use. How do I improve it?
**A:** Emphasize production context:
```
PRODUCTION CONTEXT: This system will handle [specific scale/criticality].
Assume hostile environment with unreliable dependencies.
Include comprehensive error handling and monitoring.
```

### Q: What if the verification checklist items conflict with each other?
**A:** This usually means you need a hybrid approach or should reconsider your scenario choice:
1. Review scenario choice: Maybe you need a different base prompt
2. Prioritize conflicts: Which requirement is more important?
3. Custom checklist: Create your own based on your specific needs
4. Staged approach: Meet some requirements now, others later

## 🤝 Contributing

### Q: How do I report issues with existing prompts?
**A:** Create a GitHub issue with:
1. Which prompt you were using
2. What you were trying to build
3. What went wrong (AI output, process issues, unclear instructions)
4. What you expected instead

### Q: Can I contribute new scenario prompts?
**A:** Yes! We welcome new scenarios. Use the template in `/templates/new-prompt-template.md` and ensure:
- The scenario addresses a real development context not covered by existing prompts
- It follows the CVP+ARL methodology
- Verification checklist is specific and actionable
- You've tested it with actual AI models

### Q: How do I suggest improvements to existing prompts?
**A:** Either:
1. Open an issue describing the improvement
2. Submit a pull request with the changes
3. Share your adapted version in discussions
4. Include examples of how the improvement helps in real scenarios
