# Claude Certified Architect Foundations

This repository is a starter project for the Claude Certified Architect Foundations (CCAR-F).

## Getting Started

I created the project at ~\ccar-f-study. It has one hub agent and four spoke agents, and I haven't run any of them yet.

Agents (in .claude\agents\):

┌──────────────────────┬───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│        Agent         │                                                             Role                                                              │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ study-coordinator    │ The hub. It splits the request, delegates to the spokes, and saves the final lesson to lessons/.                              │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ concept-researcher   │ Pulls definitions, trade-offs and failure modes from Anthropic docs, with sources. Anything it can't confirm is tagged        │
│                      │ UNVERIFIED.                                                                                                                   │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ example-builder      │ Builds one worked example with an ASCII diagram, a step-by-step walkthrough, a failure case and an anti-example.              │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ exam-question-writer │ Writes 6 scenario-based multiple-choice questions, each with an explained answer.                                             │
├──────────────────────┼───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│ study-synthesizer    │ Merges everything into one lesson with a cheat sheet, a self-check list and open items.                                       │
└──────────────────────┴───────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────────┘

The hub runs the researcher first. It then runs the example builder and the question writer in parallel, and finishes with the synthesizer. Spokes never call each other, so the project itself shows the pattern you're studying.

To use it: open Claude Code in ccar-f-study, then ask Use study-coordinator to teach me hub-and-spoke orchestration.

Limits:
- I don't have the official CCAR-F exam guide, so the agents can't know the real domain weights or question style. Check the official guide yourself.
- If you have the exam guide as a file or link, I can add its objectives so the agents map each lesson to them.
- Agent files load when a session starts, so restart Claude Code in that folder before first use.


## License

This project is licensed under the MIT License.
