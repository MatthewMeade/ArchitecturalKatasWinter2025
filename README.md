# Iterative Strategies

The Iterative Strategies Architects group is a team formed for participating in Architectural Katas - Winter 2025

---

# Introduction and Goals

<!-- https://docs.arc42.org/section-1/ -->

## **Mission**

Our mission is to help **Certifiable, Inc** scale sustainably its processes and operations to meet its increasing demand by presenting an architectural proposal that intends to optimize the different parts of the workflows by leveraging AI technologies and strategies with the ultimate goal of decreasing the required time for the certification process to be completed.

## Team Members

- [Matthew Meade](https://www.linkedin.com/in/matthewmeade/)
- [Agustin Gomes](https://www.linkedin.com/in/agustingomes)
- [Vasileios Chroniadis](https://www.linkedin.com/in/chronvas/)
- [Bryte Henry](https://www.linkedin.com/in/bryte-h/)
- [Tyrone Jones](https://www.linkedin.com/in/tyronefjones/)



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


## Quality Goals
<!-- 
    - Top 3-5 quality goals for the architecture in a table
    - Note: Goals for the artecture itself, not the product
    - For example reliability, security, sustainability

    Example
    - https://docs.arc42.org/examples/quality-tpu-1/
-->


# Architecture Constraints
<!-- 
    https://docs.arc42.org/section-2/ 

    - Any requirement that constrains the design and implementation, a simple list

    Example: 
    - https://docs.arc42.org/examples/constraints-1/
-->

- The new Architecture must fit into the existing implementation


# Context and Scope
<!-- https://docs.arc42.org/section-3/ -->

## Business Context
<!--
    - The context of business stakeholder's point of view. What data is exchanged and the environment
    - Diagrams shoing the system as a black box, specifying the interfaces with stakeholders
    - Alternatively (or additionally) you can use a table. The title of the table is the name of your system, the three columns contain the name of the communication partner, the inputs, and the outputs.

    Examples
    - https://docs.arc42.org/examples/business-context-1/
    - https://docs.arc42.org/examples/context-business-2/
    - https://docs.arc42.org/examples/business-context-3/

-->

## Technical Context
<!-- 
    - Technical interfaces linking the system to its environment, I/O
    - Interactions with external services or hardware. An example for our project would be if we're interfacing with an external managed AI service?

    Examples
    - https://docs.arc42.org/examples/technical-context-1/
    - https://docs.arc42.org/examples/technical-context-4/

-->


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



# Runtime View
<!-- 
    https://docs.arc42.org/section-6/

    - This section describes concrete behavior and interaction of the system's building blocks in the form of scenarios
    - Important use cases or features, how they're executed
    - Interactions at critical interfaces
    - Operation and administration - launch, start, stop
    - Error and exception scenarios

    - Note: 
        - The main criterion for the choice of possible scenarios (sequences, workflows) is their architectural relevancy. 
        - It is not important to describe a large number of scenarios. You should rather document a representative selection.

    - Possible scenario notations
        - Numbered list of steps
        - Activity diagrams or flow charts
        - Sequence Diagrams
        - BPMN or EPCs
        - State Machines

    Examples:
    - https://docs.arc42.org/examples/runtime-1/
    - https://docs.arc42.org/examples/runtime-mama-2/
    - https://docs.arc42.org/examples/runtime-tpu-1/
-->


# Deployment View
<!-- 
    https://docs.arc42.org/section-7/

    (We don't have much detail on how the current system is deployed, so not sure how we would deal with that here)

    - Technical infrastructure used to execute the system
    - Elements like geographical locations, environments, hardware, channels, topoligies
    - Mapping of what software runs on which infrastructure elements
    - Can include any different environments, eg if we have prod and testing environments
    - Only include the level of detail necessary

    Example 1
    - https://docs.arc42.org/examples/deployment-1/
    - https://docs.arc42.org/examples/deployment-htmlsc-1/
    - https://docs.arc42.org/examples/deployment-2/
-->


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


# Quality Requirements
<!-- 
    https://docs.arc42.org/section-10/ 

    Make sure to include the high priority goals added in the introduction section
-->

## Quality Tree
<!-- 

    - Table or tree of quality requirements with quality/evalutation scenarios
    - ATAM format: https://en.wikipedia.org/wiki/Architecture_tradeoff_analysis_method
    - Include links to the 'quality scenarios' section

    Example:
    - https://docs.arc42.org/examples/quality-tpu-1/
-->

## Quality Scenarios
<!--
    - Explanations of quality requirements 
    - Descrive what should happen when some stimulus occurs
    - Usage scenarios
        - the system's runtime reaction: efficiency  or peformance
        - Eg the system reacts to a user's request in one second
    - Change scenarios
        - describe a modification of the system or its environment
        - eg: requirements change (needing to change LLMs?)


    Example:
    - https://docs.arc42.org/examples/quality-htmlsc-2/
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