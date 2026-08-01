## SDLC (Software Development Life Cycle)
 * **SDLC:** Software Development Life Cycle
 * SDLC is a structured process used by software teams to plan, design, build, test, and deliver high-quality software to meet business requirements.
### How it manages?
<pre>
 Business Analyst
        │
        ▼
Business Requirement
        │
        ▼
Requirements Gathering
        │
        ▼
Planning and Designing
        │
        ▼
Implementation (Coding / Development)
        │
        ▼
     Testing
        │
        ▼
   Deployment
        │
        ▼
Release to the Public
        │
        ▼
   Maintenance
</pre>
   
## Waterfall Model
 * **Waterfall** is a traditional **Sequential model** where each phase must be completed fully before moving to the next. The main limitation is that going back to previous phases is impossible, making it very hard to incorporate changing client requirements.
### Steps in Waterfall Model:
<pre>
Step 1 :- Requirements
    │
    ▼
    Step 2 :- Design
        │
        ▼
        Step 3 :- Implementation (Coding)
            │
            ▼
            Step 4 :- Testing
                │
                ▼
                Step 5 :- Deployment
                    │
                    ▼
                    Step 6 :- Maintenance
</pre>

## Agile Model
 * **Agile Model** is an **iterative and incremental** model where the project is broken down into small cycles called **sprints (2–3 weeks)**. It delivers working software frequently, allows quick feedback, and easily accommodates changing requirements.
### Agile Methodology Cycle:
<pre>
            ┌─────────►  Plan  ─────────┐
            │                           │
          Review                      Design
            ▲                           │
            │                           ▼
          Launch ◄─── Develop (Coding) ◄─── Test
</pre>

## DevOps
 * **DevOps** is a **cultural mindset and set of practices** that bridge the gap between Development (Dev) and Operations (Ops) teams. It uses **CI/CD, automation, and continuous monitoring** to achieve faster software delivery, higher quality, and seamless collaboration.
### Why DevOps over Agile?
 * Agile solves the gap between the client and Development, whereas DevOps solves the gap between Development and Operations.
### DevOps Infinite Loop / Stages:
<pre>
 Dev Side:  [Plan] ──► [Code] ──► [Build] ──► [Test]
                                                │
                                                ▼
 Ops Side:  [Monitor] ◄── [Operate] ◄── [Deploy] ◄── [Release]
</pre>
