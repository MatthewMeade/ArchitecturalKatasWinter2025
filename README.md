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
- The expert graders receive a suggested grade and AI summary of the solution to assist in grading

Accurate AI Responses
- The AI should have access to the context it needs to grade answers accurately
- The expert grader can override the AI response with a new grade if the AI is not accurate
- When this happens it should be logged so the system can be tuned and optimized for correctness


## Quality Goals
<!-- 
    - Top 3-5 quality goals for the architecture in a table
    - Note: Goals for the architecture itself, not the product
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
    
    - The fundamental decisions and solution strategies that shape the system's architecture
    - Technology Decisions, design or architectural pattern, how to achieve quality goals, relevant org decisions and processes
    - How we are addressing quality concerns (cost, safety, etc)
    
    Examples
    - https://docs.arc42.org/examples/solution-strategy-htmlsc-1/
    - https://docs.arc42.org/examples/solution-strategy-mama-2/

-->

<!-- High level overview of the solution, breaking the architecture itself down in the building blocks section -->

## AI Preliminary Grade Flow

The overall strategy for adding AI to the existing architecture is to add an AI based preliminary grader system to the workflow for both the aptitude short answer questions and the architecture submissions. 

The new preliminary graders will read from the ungraded response databases and populate a new preliminary grade DB, which will be used by the expert graders.

Before: The manual grading stage read from the ungraded answers DB

![](./images//Before-Preliminary%20Grader%20flow.png)

After: The ungraded responses are processed by the AI grader which populates the preliminary grade DB for the manual grader to read from

![](./images/After-Preliminary%20Grader%20flow.png)


### Test 1 - Short Answers
<!-- TODO: Simple RAG. Adding the question, answer, grading criteria, etc. to the prompt -->
<!-- Since we know what material is for which question we can retrieve context by the question number without needing complex intent analysis -->
![](./images/Test%201%20Architecture.png)

The Preliminary Grader service will prompt the AI model through the gateway to generate a grade and justification.

The service will use Retrieval Augmented Generation to provide additional context to the prompt
- The original question along with any relevant grading criteria and information
- Graded answers from other candidates, with justifications

Since the questions are known ahead of time, the data being retrieved can be indexed by question ID. This reduces the complexity 
of finding relevant context


### Test 2 - Architecture Solutions
![](./images/Test%202%20Architecture.png)

Since grading the candidate's architecture solution is significantly more complex than the short answers, the Architecture Preliminary Grader service will include an Agent. 

The service will be given the original case study, grading criteria, and the candidate's submission. 

This includes the addition of a "Knowledge Base" database as a source domain specific information that can be used as context when grading the exam. 

The AI agent will:
- Determine what context it needs and retrieve it from the Knowledge Base
- Prompt the model to perform grading
- Determine if the grading criteria have been covered
- If additional context is required, get that from the Knowledge Base and prompt the model again
- Otherwise, send the grade and justification to the preliminary database for the human expert to grade

#### Knowledge Base

This database will include a store of document managed by the company including all the relevant material required to grade the exam. Expert graders rely on advanced industry knowledge when grading
submissions, this solution provides the same level of context to the AI grader.

The database will consist of a document store containing all the documentation, indexed by key terms. 

When the AI decides it requires more context on a subject based on the solution or grading criteria it finds the relevant information by providing a set of key terms.


## Metrics and Observability
<!-- TODO: The prompt orchestrator can include a component to track metrics -->

### Cost metrics

### AI Accuracy metrics
<!-- TODO: How we will get feedback from expert graders to improve the AI -->
<!-- Comparing the AI's grade with the expert grader's final grade -->


### Performance metrics


## Data Privacy and proprietary information
<!-- TODO: Talk about how we will host our own models so we don't send data to third parties -->


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

## Prompt Frameworks
<!-- TODO: Prompt / RAG / Agent frameworks -->

## Maintaining Test Integrity
<!-- TODO: Talk about how humans have the final say in grading -->

## Validating AI models
<!-- TODO: How we evaluate which model to use. Testing them against previous grades to determine how close the model is to the original expert grader  -->


# Architecture Decisions
<!-- 
    https://docs.arc42.org/section-9/

    - Important architecture decisions including rationales. 
    - We can include links to ./ADRs here
    - Order by importance, date, or something else

    Examples:
    - https://docs.arc42.org/examples/decision-use-adrs/
    - https://docs.arc42.org/examples/decision-htmlsc/
    - https://docs.arc42.org/examples/decision-tpu-1/
-->