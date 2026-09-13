# A working build protocol

**How far can one person build with AI?**

The projects in this lab explore that question through products, operational workflows, and unusual interfaces. The protocol below is the next version of the process I am trying to make repeatable. It is not a claim that every existing project already follows every step.

1. **Frame one useful outcome.** Name the user, the input, and the decision or action that should become easier.
2. **Write the boundary.** Identify what is real, what is simulated, what the model can do, and what requires a person.
3. **Divide the work.** Give coding agents bounded tasks and shared contracts. Keep integration ownership with the human.
4. **Build the smallest complete path.** Connect input to a visible result before expanding features or providers.
5. **Test failure as well as success.** Check bad inputs, isolation, retries, missing credentials, and uncertainty. Evaluate model quality separately from mocked code paths.
6. **Inspect what actually happened.** Read the diff, run the checks, and try the user interaction. Documentation and a passing mock are not deployment evidence.
7. **Publish the artifact and its limits.** Show one useful behavior, one important tradeoff, and what is still unverified.

The stronger existing work already contains pieces of this: deterministic checks, bounded tools, human confirmation, failure-path tests, and explicit handoff notes. The work now is to apply those habits consistently.

[Back to the lab](README.md)
