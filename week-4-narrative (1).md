# BUS 4040 - Week 4

---

## Slide 1 - Welcome Back

Welcome to the fourth week of BUS 4040 - AI for Business Applications

- You have configured the tools we will use for the rest of the class
- From here on, you will use AI to plan, solution, and build
- Today
  - We will cover Product Requirements
  - We will review what comprises a product requirements document, and how to ask a client the right questions
- Next week the client will be here to answer questions

## Slide 2 - The Workbench

- Is everyone connected? Claude, Mindrouter, VS Code, GitHub
- If something is broken, say something so I can help
- You will need all of it working for the remainder of the class

## Slide 3 - Why Requirements?

- AI will (try to) build almost anything you describe
- AI (currently) is not good at inventing innovative products
- The bottleneck used to be people who could write code. Now it is people who know what the code should do
- That is the job this class is training you for, and it is a business job, not a technical one
- If you write poor requirements, AI will confidently build poor product 

## Slide 4 - PRD

> A PRD Establishes a Clear Target: It takes abstract ideas floating around in brainstorms or executive meetings and grounds them into a tangible, written direction
  
> A PRD Drives Alignment: It signals to engineering, design, and marketing that "this is the problem we are solving and the territory we are claiming

> A PRD Prevents Drift: Without that initial stake, teams tend to wander, resulting in scope creep (adding too many features) or building the wrong thing entirely

- A **Product Requirements Document** defines the "what", not the "how"
- It describes what is being built and the acceptance criteria
- It is intended to be short, plain, and specific
- It is not a design, it's not code, and it's not the "how"
- At minimum it covers:
  - Who will use the product
  - What the client intends to do with the product (essential functionality)
  - What the system must do, in statements you can test (acceptance criteria)
  - What is out of scope and general constraints

## Slide 5 - A Living Document
- A PRD is the first stake in the ground, but it's not a monument set in stone
- Modern businesses set a goal and reevaluate the goal and their tactics as they approach the goal
- The process of iteration and reevaluation is commonly called "The Agile" framework

## Slide 6 - Who is a PRD for?
Everyone involved in the product lifecycle
- Product Managers (PMs): Write and update the document
- Designers: Use it to plan the user interface and user experience (UI/UX)
- Engineers: Read it to understand technical specifications and build the code


## Slide 7 - How to Ask the Right Questions
- Next week, you will meet your client
- You are not interviewing your client about software or AI
  - Technical people like to solution
  - Solutioning during the PRD process is an anti-pattern
- Your goal is to gather product requirements to build the correct solution
- Some habits that separate a useful question from a wasted one:
  - **Ask about the past, not the future.** People are less accurate about the future. They remember what worked and what didn't work
  - **Ask for the exception.** The normal case is easy. The value is in the weird one.
  - **Do not ask the client to design.** The client is the expert on the problem. You are responsible for the solution. Avoid solution based dialogue.
  - **Avoid questions that are already answered.** That is the fastest way to waste your time and your client's time
- Here are some examples,

| Weak | Better |
|---|---|
| "What features would you want in a speaker database?" | "Tell me about the last time you had to look up a past speaker. What did you do?" |
| "Should we merge duplicate speaker records?" | "If someone spoke in 2018 as a utility VP and in 2024 as a consultant, is that one speaker or two?" |
| "Should search be a dropdown or a text box?" | "When you look up a past speaker, what do you usually already know about them?" |
| "What years do you have data for?" | "Some agendas list a speaker who may not have shown up. Should a cancelled speaker still count?" |
| "Do you want a schedule builder?" | "Walk me through how you built your last event schedule. Where did you start?" |
> Ask clients about past interactions and current pain points. Write your questions down before you meet the client. Be flexible, but don't go into a client interaction cold and try to improvise

## Slide 8 - The Project

- The client is real, the data is real, and the handoff at the end of the semester is real
- CBE runs executive education for the energy sector through three programs: 
  - The Energy Executive Course
  - The Energy Executive Summit
  - The Legislative Energy Horizon Institute
- You will receive event schedules and agendas, 2016 through 2026
- The files were manually created by different people, and the formats drifted
- All of it is public. Nothing you touch is confidential
- Consultants are discrete and respectful about shared information 
- High-level, the client would like
  1. Organized data
  2. Standard format
  3. Add, edit, and delete records
  4. Search
  5. Analysis
  6. Backup and restore
  7. Build a new event schedule

## Slide 9 - Teamwork

- Four teams of four
- Each team will be provided a private repository in the course GitHub organization.
- Pull Requests will have to be approved by your teammates
- Part of your grade is based on teamwork, which is why the first thing you write together is a social contract
- Find your team before you leave today and agree on a time to meet this week

## Slide 10 - Homework

- Full detail is in **week-4-homework.md**
- The short version:
  1. Every member connects to the team repo and confirms they can open a pull request
  2. The team writes a social contract and commits it
  3. The team drafts a rough PRD in the `./prd` folder
  4. Each member opens a pull request with one question for the client
- The questions are due before class next week so I can group them. Late means unasked

## Slide 11 - Next Week

- The client is here for the full period
- They will be answering your questions, not giving a lecture
- If everyone asks one question, there about three minutes available for each answer
- After she leaves, you will find out how much of your draft was a guess


