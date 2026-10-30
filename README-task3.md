# Sprint #3: Feature Work

## Overview
In this Sprint, you will implement!! All work should be tracked by a Work Item in Kanban. Especially important is to have work items for everything needed in this sprint, and to assign owners of the work.   

**Tasks:**  
* Each member of the group will develop a medium-sized feature in their own branch that will get merged into `main`. 
* Each member will test someone else's feature. 
* The group will have a Discord bot for `main` so that all features can be tested in one spot.  
* The group will create a Tag of the *release*.  
 

**Deliverables in GitHub:**  
* There is a Kanban work with text describing your feature as User Story. It should contain other important information about the feature to "Define Done".  
* There is a Kanban Validation work with text describing your feature's Test Scenarios.    
* GitHub should contain your branch for your feature work, and that work should be merged into `main`.  
   - Your feature is functional.  
   - Your feature has tests that run with `npm test`. (Use AI to help)  
* A Burndown graph will be created by scripts using your Work Items. The Kanban board on GitHub should reflect consistent progress.      
* Create a Git Tag v1.0 with all the team members' contributions. This should be a Work Item on the Kanban board for one member to complete.  

**Prepare:**  
* In class, you'll fill out a survey as you and a peer review your understanding of the work in this task.  

**The goals:**  
* Continue with an insulated work environment:  
   - Each student works on their own **Codespace instance**.
   - Each student works on their own **git branch** (that runs in their own Codespace).  
   - Exercise branches, pull requests, tests, Kanban  
* Work in a environment where many developers simultaneously create multiple features and merge them into one `main`.   
* The TEAM will create a singular, `main` Discord Application, Discord server, and Discord bot  
   - Success means that everyone's code, once merged into main, can be tested in a shared Discord server.  

**Steps:**  
1. As a group, brainstorm some Discord bot features.  
2. Assign one or more significant features to each team member.  
3. Create work items for creating `main` Discord Bot.  
4. Create a work item for creating the git *tag*.  
5. Break up Feature into smaller User Stories. 
6. Create a Validation work item assigned to someone else.  
7. Use AI to develop and to create Unit Tests for feature work.  
8. Complete all Sprint work, updating work items regularly.  

## Create a Kanban Work Items
Read the all the steps above and below to get an idea of what you'll create in this task. Create new 
Backlog items and add them to the Kanban board's backlog. Assign them to someone on the team and,
as you make progress, track the work on the Kanban board.  
Make sure that you include work to create Unit Tests, that you have a Validation work item with Test Scenarios, and that you include work that the team needs to do. 

## Create `main` Discord bot  
**Only one person does this.**
One teammate creates a Discord server for the team and invites everyone else to it. Be sure to share the invite link with the team (e.g., pin it in your team's chat or add it to the repo's README).  

Recall the steps to create a Discord bot are found in the instructions for Sprint #1. Someone will have to redo these for the merged work that lives on `main`.  
1. Create a Codespaces on main  
2. Assure that `main` has an `.env` file with secrets  
3. Create a new Discord Application. Install and Register it. 
4. Create a Test Server on Discord. Invite your group to participate on it.  
5. Install npm, register commands, start the bot, make the port public.  
6. Verify that everyone can interact with the main bot. 

Everything below this point, **each student does individually**, on their own
branch.


> **Important**:  
>> While it is common to frequently create and delete branches, in this project **KEEP** all your branches so that Stride (and graders) can examine your individual work.  **Never delete** any of your branches.

---

**A few things to watch for:**
- If `commands.js` changed, you must re-run `npm run register`, or Discord's
  slash command list won't reflect the change.
- If the Codespace running `main` is ever deleted and recreated, its forwarded
  URL will change — remember to update **that** application's Interactions
  Endpoint URL in the Developer Portal, the same way you did for your personal
  bot in Step 6.
- Decide as a team how to coordinate updating the deployment Codespace instance. You don't want to clobber one another as the server is updated. Similarly, you don't want to assume that someone else will do the work for you.
- For more complicated features added, you may need to `npm install` if `package.json` was updated with new Node packages.
- You are free to create a new branch if you like. Once you have the Codespace referencing the code in your new branch, you'll simply need to stop & start the service. There is no need to create a new Codespace instance, nor a Discord App, as these can be reused.  
- If you do all your work in the same personal branch, make sure to pull the latest code in `main` into your branch before starting new work; you don't want to build on stale code!This is technically a `merge` of main into your branch.  

## Q & A

**1. Why does each student need their own Codespace, branch, and Discord Application?**

Each student needs an isolated environment so they can work independently without interfering with someone else's bot, port, or URL. This prevents conflicts when multiple people run the server at the same time or try to register commands in the same shared setup.

**2. What is the difference between a Git branch and a Codespace in this project?**

A Git branch is a version of the repository's history that lets you work on changes separately from `main`. A Codespace is the cloud-based development environment where that branch is opened and edited. One branch can be used in one or more Codespaces, but each Codespace is a separate place to run and test your work.

**3. Why is `.env` created separately in each Codespace instead of being shared?**

Each Codespace has its own bot configuration, including its own Discord Application credentials and forwarded URL. Sharing one `.env` would cause the wrong bot token, public key, or endpoint URL to be used, which would break testing and deployment.

**4. What must you do after changing slash commands in `commands.js`?**

You must re-run `npm run register` so Discord updates its list of available slash commands. Without re-registering, your new command may not appear in Discord even if your server code is already running.

**5. What is the purpose of a pull request in this workflow?**

A pull request is the review step before merging your branch into `main`. It gives teammates a chance to inspect the code, discuss changes, and confirm that the feature is ready before it becomes part of the shared project.

**6. Why do you need to coordinate updates to the shared bot running from `main`?**

The bot running from `main` is a shared deployment environment, so only one person should update it at a time. Coordinating changes prevents one update from overwriting another and helps ensure the team is testing the same version of the app.
