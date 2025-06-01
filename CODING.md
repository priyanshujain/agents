How we write our code with the help of AI agents. Software engineers are split on this subject. Many think it’s the most transformative tech ever built; others say it’s hype. Personally, I feel like I get a lot of value from AI. I want to dig a bit into the fundamentals and how I use it efficiently.

At the core, an agent is an LLM with access to tools that manipulate text. There are many coding agents out there right now, but most of it is an LLM in a loop and the rest is elbow grease. The model itself still drives most of the effectiveness.
Agents can use various tools such as file editing, running terminal commands to accomplish tasks. Our goal should be to utilize the agent for specific tasks to make the tool work well with model. Use model which has a better tools support, Claude 3.7 is the best right now with the tool support but performance can vary on different tasks.

How I use agents -

First, Setup. Add context for agent like commands, workflows, and project guidelines to CLAUDE.md or AGENTS.md(depends on the agent you are using). This saves a ton of time on feedback loops and improves quality.

If jumping into a new codebase then use the agent as a colleague to explain code line by line. Make sure to ask specific questions as generic questions blow up the context size and take a lot of space in context window.

Give clear instructions. If it’s an integration, point the agent to relevant docs or links. Specificity matters. Again, generic prompts are a trap they consume context and often don’t help.

Ask the agent to create an architectural plan and break the work into tasks. Save this in a plan.md or similar. Then implement it one task at a time. Ideally, each task should be testable in isolation.

Agents make test writing easy use that. Write end to end tests so you know new changes don’t break things.

Target one task each coding session so agent can hold the context for the task as there is a limited context window a model can hold.

Before asking for code, ask the agent to reason about the problem. This is a general philosophy ask agent to explain the solution in clearest form before implementing, it helps agent define the solution before implementing. 

Write the test for the task and then the implementation. Test gives clarity about the feature and allows us to refactor later. So first implement working but throwaway code just so the test passes.

Use agent in full mode where it can compile and run tests on it’s own, analyze errors with squiggly lines, correct the errors and run the tests again.

Once tests pass then refactor the code to match production quality as it becomes easy with tests. Before committing, proofread and check for typos. Commit regularly to revert to working versions if the agent makes errors.
