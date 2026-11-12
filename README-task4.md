# Sprint #4: Analysis

## Overview
Each team member will contribute to the analysis of the Discord Bot.  

**Task:** 
* Identify bugs, gaps, and technical debt in your bot and start closing the gaps  
* Complete a Security Analysis: STRIDE, Threat Tree  

**Deliverables:**  
You are done if you have conducted an analysis of limitations and weaknesses in your assigned bot and completed the following:
1. Publish `report.md` to the main group repository (everyone from the group should contribute to this single report). Each person should have their own dedication section that has their name. Example: `## Stride's Section`   
2. Create user stories drawn from both the problems you've found and any new ideas for improving your bot that arise through this process.  
3. Create a v2.0 Tag in Git  

No artifact turned into Canvas is required. Stride will grade the state of your git repository and project board.  

**Steps:**

1. Divide up the different perspectives on code analysis and code hardening into tasks for each group member, choosing one from the following:
   - Examine your code for technical debt and code smells.  
   - Assess the cyclomatic complexity of the methods in your bot.  
   - Measure your cohesion and coupling (architecture diagrams might help with this!).  
   - Measure your test coverage.  
   - Build a threat model.  
   - Write a fuzzer to try to break functionality in your bot (see Fast-check for a short intro to running fast-check tests in Codespaces).  
   - Unit tests. Write at least 3, these are easy and quick.  
   - Smoke test. If you don't have one already, write a test that will call all the major functions in your bot and verify that core features are working.  
   - Implement continuous integration / continuous deployment for your bot.  
   - Your own idea about what the bot needs  
2. Describe your efforts and findings in a shared code analysis report in your repo.
3. Create user stories associated with your findings (at least 1 per person; you must write out the story yourself).  

**Tips:**
* Think about how your bot has been used so far. What did your testers say? Did anyone try anything that didn't work or wasn't supported? Maybe that's a bug or feature request?  
* Think back to when you were writing the bot. Did you cut any corners or implement something quick and dirty, planning to come back to it later?  
* Think like a bad actor: what happens if you try to break your bot?
* Feel free to use AI tools as a tutor or source for debugging any issues that come up, however you are responsible for the content you turn in.  

## Tests
* You should have a folder named `test`.   
* Files in that folder that have tests should be named: `*.test.js`.   
* run the tests with `node --test` in the terminal window.  

```javascript

import test from 'node:test';
import assert from 'node:assert/strict';

import {
  myMethodToTest,
} from '../commands/my_command.js';

test('sample test of myMethodToTest', () => {
  assert.equal(myMethodToTest(), 1);
});
```

You could also modify `package.json` to have:
```json
"scripts": {
  "test": "node --test",
  "test:coverage": "node --test --experimental-test-coverage"
}
```
The code coverage feature is an experimental feature available in node version 20+.  

Then you can do: `npm run test:coverage` or just `npm test`.



## Q & A
**1. Discuss the differences in `orig` and `modular-architecture`. Are the differences considered "architectural" or "design" in nature? Is modular better? Why?**  

*Are the differences architectural or design?*   
**BOTH!!** — If we focus on the **Discord Bot** itself, this would clearly be **Architectural** because this is a fundamental structural reorganization of the entire bot code, not just implementation details of a single command. However, if you look at **Discord** as a whole, at a higher level--where we have the Discord Platform, Discord Application, JSON communication protocols defined over HTTPS, with a browser or a Discord application--then the Discord Bot is a small portion of the overall architecture. In which case, file organization and modular structure looks more like Design.  

> Truth be told, it doesn't really matter that much. Call it whatever you want. :-)  

**Modular is significantly better** because:

1. **Low coupling**: Commands don't interfere with each other
2. **High cohesion**: Each command is self-contained
3. **Reduced merge conflicts**: Multiple developers can work in parallel
4. **Smaller cognitive load**: Developers understand less code to make changes
5. **Fewer bugs**: Isolation prevents accidental side effects
6. **Better scalability**: Adding features doesn't require editing existing files

The monolithic approach works fine for a small, single-developer prototype, but the modular approach is the correct choice for any project that will grow or be maintained by multiple people.