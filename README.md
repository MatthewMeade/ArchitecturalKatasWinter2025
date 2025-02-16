# Iterative Strategies

The Iterative Strategies Architects group is a team formed for participating in Architectural Katas - Winter 2025


## Team Members

- [Matthew Meade](https://www.linkedin.com/in/matthewmeade/)
- [Agustin Gomes](https://www.linkedin.com/in/agustingomes)
- [Vasileios Chroniadis](https://www.linkedin.com/in/chronvas/)
- [Bryte Henry](https://www.linkedin.com/in/bryte-h/)
- [Tyrone Jones](https://www.linkedin.com/in/tyronefjones/)


---

# Introduction and Goals

<!-- https://docs.arc42.org/section-1/ -->

## **Mission**

Our mission is to help **Certifiable, Inc** scale sustainably its processes and operations to meet its increasing demand by presenting an architectural proposal that intends to optimize the different parts of the workflows by leveraging AI technologies and strategies with the ultimate goal of decreasing the required time for the certification process to be completed.




## **Challenges**

Considering the rapid evolution of AI technologies and ecosystem, combined with the nature of the LLM responses being non-deterministic, The sanitization of the information exchanged with the models remains one of the most challenging aspects of implementing AI technologies due to the natural language characteristics these systems possess, which poses the risk of returning irrelevant information for our context.


## Requirements Overview
<!-- 
    - Short description of the functional requirements
    - From the point of view of the end users
    - Short text description, possibly in a table. 
    - Link to more detailed requirements documentation

    Examples
    - https://docs.arc42.org/examples/overview-example-htmlsc-1/
    - https://docs.arc42.org/examples/overview-example-3/

 -->

The job to be done of adding AI to the existing architecture is to assist the expert graders by reducing the time it takes to grade an exam.

Grading Aptitude Tests
- The expert graders receive the question to be graded with a suggested score and justification

Grading Architecture Solutions
- The expert graders recieve a suggested grade and AI summary of the solution to assist in grading

Accurate AI Resposnes
- The AI should have access to the context it needs to grade answers accurately
- The expert grader can override the AI response with a new grade if the AI is not accurate
- When this happens it should be logged so the system can be tuned and optimized for correctness


## Quality Goals
<!-- 
    - Top 3-5 quality goals for the architecture in a table
    - Note: Goals for the artecture itself, not the product
    - For example reliability, security, sustainability

    Example
    - https://docs.arc42.org/examples/quality-tpu-1/
-->
The top quality goals for the architecture

1. Costs of running the new AI system
2. Scalability, the system handle the 5-10x growth in global users along with the 21% yearly growth
3. Maintaining the accuracy and integrity of the exams



# Architecture Constraints
<!-- 
    https://docs.arc42.org/section-2/ 

    - Any requirement that constrains the design and implementation, a simple list

    Example: 
    - https://docs.arc42.org/examples/constraints-1/
-->

- The new Architecture must fit into the existing implementation
- Maintaining a low cost is a high priority


# Solution Strategy
<!-- 
    https://docs.arc42.org/section-4/ 
    
    - A short summary aof the fundamental decisions and soultion strategies that shape the system's architecture
    - Technology Decisions, design or architectural pattern, how to achieve quality goals, revelant org decisions and processes
    - Table or list
    - Link to later sections 5 or 8 for more details
    
    Examples
    - https://docs.arc42.org/examples/solution-strategy-htmlsc-1/
    - https://docs.arc42.org/examples/solution-strategy-mama-2/

-->


# Building Block View
<!-- 
    https://docs.arc42.org/section-5/

    - The static decomposisition of the system as building blocks
    - Modules, components, interfaces, dependencies with relationships and associations
    - Hierarchial collection of diagrams and descriptions

    Levels
    - Level 1: white box description of the overall system together with black box descriptions of all contained building blocks.
    - Level 2: zooms into some building blocks of level 1
    - Level 3: zooms into some building blocks of level 2
    - ...
    - Level n: ...

    Examples:
    - (all levels) https://docs.arc42.org/examples/buildingblock-hsc/
    - (level 1) https://docs.arc42.org/examples/buildingblock-tpu-1/
    - (level 2) https://docs.arc42.org/examples/buildingblock-tpu-2/
-->

## Overall System 
<!-- 
    https://docs.arc42.org/section-5/#51-whitebox-overall-system

    - The decomposition of the overall system using the white box template
    - An overview diagram
    - A motivation for the decomposition
    - Black box descriptions of the building blocks. A list or a table

    Example
    - https://docs.arc42.org/examples/buildingblock-tpu-1/
-->


## Level 2
<!-- 
    - Specify the inner structure of some of the blocks from level 1
    - Please prefer relevance over completeness. Specify only important, surprising, risky, complex or volatile building blocks. 

    Example
    - https://docs.arc42.org/examples/buildingblock-tpu-2/
-->

## Level 3
<!-- 
    - Specify the inner structure of some of the blocks from level 2

-->


<!-- ## Level n ... Not sure how deep we need to go, I'd assume 3 is enough -->


# Implementation Details
<!-- 

    Note: This is called "Crosscutting Concepts" by arc42, but I didn't think that was a good title for the section

    https://docs.arc42.org/section-8/

    Principal regulations and solution ideas that are relevant in multiple parts of the system, such as:
    - Domain Models
    - Architectural patterns or design patterns
    - Rules for using specific technology
    - Implementation rules

    Suggested structure
    - Domain concepts
    - User Experience concepts (UX)
    - Safety and security concepts
    - Architecture and design patterns
    - “Under-the-hood” concepts
    - Development concepts
    - Operational concepts

    Examples:
    - Within a system, a common format for log-messages shall be established, combined with a common convention of choosing the appropriate log-destination. These decisions, along with implementation examples, could be described as “logging-concept”.
    - A system has numerous backend services, that communicate among each other based upon remote procedure calls or http-based REST. Calling services (“consumers”) always need to authenticate themselves to the called service (“provider”). For this authentication, a central common authorization service has to be used. The technical and organizational details such authentication could be described as “backend authentication concept”.
    - https://docs.arc42.org/examples/concept-htmlsc-1/
    - https://docs.arc42.org/examples/concept-htmlsc-2/
    - https://docs.arc42.org/examples/concept-tpu-1/
    - https://docs.arc42.org/examples/concept-tpu-2/
-->


# Architecture Decisions
<!-- 
    https://docs.arc42.org/section-9/

    - Important architecture decisions including rationailes. 
    - We can include links to ./ADRs here
    - Order by importants, date, or something else

    Examples:
    - https://docs.arc42.org/examples/decision-use-adrs/
    - https://docs.arc42.org/examples/decision-htmlsc/
    - https://docs.arc42.org/examples/decision-tpu-1/
-->



# Risks and Technical Debts
<!-- 
    https://docs.arc42.org/section-11/

    - Identified technical risks or debts ordered by priority
    - Include suggested measures to minimize, mitigate, or avoid risks

    Examples:
    - https://docs.arc42.org/examples/risk-htmlsc-1/
    - https://docs.arc42.org/examples/risk-tpu-1/
-->


# Glossary
<!-- 
    https://docs.arc42.org/section-12/

    - Important domain and technical terms stakeholders use when discussing the system
    - Table with term and definition columns

    Example:
    - https://docs.arc42.org/examples/glossary-1/
-->