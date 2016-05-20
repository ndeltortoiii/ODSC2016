# Superpower your Analytics Team with Technical Agile a How to Guide
## Chris Bergh, Gil Benghiat, Eric Estabrooks
* Data loading and prep, not just the responsability of ETL Team
* Prepare, analize, and communicate expectations are very different for work required
* softare there to teach analytics about how to deal with complexity
  1. Agile process and 
  2. Technical environment (7 shocking steps)

### Agile manifesto (http://www.agilemanifesto.org/)
*3.0 learning organization

* Exercise 1
  * What mechanisms can you put in place to help your organization learn (About product or process)?
  * Through retrospectives
  * How do you know you have the right people: volunteer, have been through it before

* Velocity
  * Build what is most important first
  Elminate waste
  REmove impediments
  Reduce overhead from context switching

* Prescriptinve vs. Adaptive
  * RUP --> XP --> Scrum --> Kanban --> _____
  
* Scrum: Team performance and delivering value (Analytics and Models)
  * 16 pages
  * Product Owner: Maximize the business value to the team
  * Team, Meetings, Artifacts
  
* Sprint Planning, Daily Scrum Meetings (15 minutes max for whole team), Retrospective
  1. what did i do yesterday
  2. what's my goal for today
  3. are there any impediments

* Structure, story, prop, elemnt 1, element 2

* Features (Through each sprint), Learning and Value (At the end of each sprint)

* Exercise 2 How can you divide your work to deliver value?
  * If model going into an operational system and the model is being built out in parallel
    * have your interface between the model and the system design, *build that out first**
    * (Think we are doing this by building out the BI tool)

* Story points
  * measure the effort required to implement a story
  * Simple terms have a number tha tells the value of the story
  * Scales / Baseline story: fibonacci, exponential, t-shirt, truncated fibonacci (non-linear for rough orders of magnitude)
  * Estimates used for decision making, for planning NOT punishment
  * Story
    * As a <role>, I want <result>, so that <context>
      * no how
      * Actionable ? implementable / complete
      * Small
      * Testable
  * Retrospective option 1--pick improvements you want to do next
    1. Start doing
    2. Stop doing
    3. continue doing
  * Rerrospective option2
    1. scale of 1 to 5 how you feel about your role in the company
    2. same scale, how do you feel about the company as a whole
    3. Why do you feel that way?
    4. What one thing would make you happy
    
* Exercise 3 If you had a magic wand, what are three impediments you would remove
  * Non standard file formats
  * beurocracy
  * budget
  * Client micro manage the team they were hired
  * Sales people misrepresenting
  * Legacy softwawre completly unsupported


    
* WIP = Work In Progress
  * Kanban practice to limit the amount of WOrk in Progress
  * benefits: less context switching more velocity

* Jeff Sutherland -- reduce context switching
* Sales people are notorious about it
  * managers vs. makers time

### Seven Shocking Steps (Analytics, Operation, Driven, Technical
* Have a safe place (Test environment) to work
* Experiments of models

1. Add Continuous tests
  * Deming (https://en.wikipedia.org/wiki/W._Edwards_Deming)
  * Types (Prove that it is right)
    1. Error--stop the line (Input file row count way below a critical threshold)
    2. Warning--investigate later (Input file row count a little below a threshold)
    3. Info--list of change (These customers changed territories)
  * Are inputs free from issues?
  * Are your business logic assumptions still true?
  * Are your outputs consistent?
  * Types
    * Conformity, 
    * completelness, 
    * range, 
    * process control totals, 
    * baseline / minimum epectation counts, 
    * historical balancing, 
    * referential integrity, 
    * rules / ratios / relationships  
  * Be sure to save your test results
  * Exercise 4 List 5 examples of data tests you might add
    1. is anyone still using this data 
    2. multi step ingestion process
    3. compare against updated standard
    4. Lifegaurd proactive not reactive
    5. check data types
    
2. Do branching and merging
3. Use Multiple Enviro
4. Modularize and Containerize
5. Give analyst knobs
6. Use simple storage
7. SUpport Three Workflows
