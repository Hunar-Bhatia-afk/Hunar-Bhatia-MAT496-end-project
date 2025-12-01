Template for creating and submitting MAT496 capstone project.

# Overview of MAT496

In this course, we have primarily learned Langgraph. This is helpful tool to build apps which can process unstructured `text`, find information we are looking for, and present the format we choose. Some specific topics we have covered are:

- Prompting
- Structured Output 
- Semantic Search
- Retreaval Augmented Generation (RAG)
- Tool calling LLMs & MCP
- Langgraph: State, Nodes, Graph

We also learned that Langsmith is a nice tool for debugging Langgraph codes.

------

# Capstone Project objective

The first purpose of the capstone project is to give a chance to revise all the major above listed topics. The second purpose of the capstone is to show your creativity. Think about all the problems which you can not have solved earlier, but are not possible to solve with the concepts learned in this course. For example, We can use LLM to analyse all kinds of news: sports news, financial news, political news. Another example, we can use LLMs to build a legal assistant. Pretty much anything which requires lots of reading, can be outsourced to LLMs. Let your imagination run free.


-------------------------

# Project report Template

## Title: Multi-Step Coding Research Agent using LangGraph, Tool Calling, and Semantic Search

## Overview

This project builds an advanced AI agent designed to act as a comprehensive coding and developer tool research assistant.

Here's an overview of what it exactly does:

Multi-Step Research: Unlike a simple chatbot, the agent follows a pre-defined, multi-stage workflow using LangGraph. This ensures a predictable and consistent research process.
Web Data Retrieval (RAG & Tool Calling): It leverages Firecrawl (via its SDK, which functions as a tool) to perform web searches and scrape content from various websites. This retrieved information then augments the LLM's knowledge.
Intelligent Data Extraction & Analysis (Structured Output): It uses a powerful technique called Structured Output with Pydantic models. This forces the underlying Large Language Model (LLM) to extract specific information (like pricing models, tech stacks, API availability, descriptions) from the scraped web content and present it in a clean, organized format, rather than just free-form text.
Recommendation Generation: Finally, after gathering and analyzing data on multiple tools, the agent uses the LLM to provide concise recommendations based on the initial query and the collected data.
In essence, it automates and structures the process of researching programming tools, providing clear, actionable insights.

## Reason for picking up this project

### This project strongly aligns with the course content by providing a practical implementation of several key AI and LLM concepts:

#### Prompting: The project extensively uses various prompting strategies. This includes crafting clear system prompts to define the agent's persona and instructions (e.g., "You are a helpful assistant that can scrape websites...") and user prompts that guide the LLM's task at each stage (e.g., extracting tools from article content). This demonstrates effective communication with the LLM.

#### Structured Output: A core feature of this project is its ability to produce highly organized and usable data. By integrating Pydantic models (CompanyAnalysis, CompanyInfo, ResearchState) with the LLM's with_structured_output capability, the project explicitly forces the LLM to output information (like pricing, tech stack, API availability) in a predefined JSON-like schema, ensuring data validation and downstream processing.

#### Semantic Search: The project employs Firecrawl's search functionality, which goes beyond simple keyword matching. When the agent searches for "best Firebase alternatives" or "Google Cloud alternative," it aims to understand the context and intent of the query to retrieve highly relevant articles and information, showcasing an application of semantic search principles.

#### Retrieval Augmented Generation (RAG): This project serves as an excellent example of a RAG system. It systematically:

Retrieves external, up-to-date information by searching the web and scraping article content using Firecrawl.
Augments the LLM's knowledge base by providing this retrieved content as context in the prompts.
Generates highly informed and relevant responses (tool lists, analyses, recommendations) that are grounded in the real-time web data rather than just the LLM's pre-trained knowledge.
Tool Calling (LLMs & MCP): The project demonstrates sophisticated tool integration. Initially, it shows how an LLM can abstractly call tools via an MCP (Model Context Protocol) server. More importantly, the advanced agent illustrates explicit tool calling by writing Python code that uses the Firecrawl SDK to manually execute web scraping and search functions. The LangGraph workflow then orchestrates when and how the LLM decides to invoke these specific tools to accomplish its multi-step research.

#### LangGraph: State, Nodes, Graph: The entire advanced agent is built upon the LangGraph framework, directly addressing these concepts:

##### Graph: The project constructs a directed graph of operations (extract_tools_step, research_step, analyze_step), providing a clear visual and logical flow for the agent's execution.
##### Nodes: Each distinct step in the research process is defined as a separate "node" or function within the graph, making the workflow modular and manageable.
##### State: A central ResearchState object (a Pydantic model) is utilized to maintain and pass information (like query, extracted tools, companies, analysis) between the nodes, ensuring that data collected in one stage is accessible and updated in subsequent stages of the workflow.

____________________________________________________________________________________________________________________________________________________

## Video Summary Link: 

Make a short -  3-5 min video of yourself, put it on youtube/googledrive, and put its link in your README.md.

- you can use this free tool for recording https://screenrec.com/
- Video format should be like this:
- your face should be visible
- State the overall job of your agent: what inputs it takes, and what output it gives.
- Very quickly, explain how your agent acts on the input and spits out the output. 
- show an example run of the agent in the video


## Plan

I plan to execute these steps to complete my project.

- [Done] Step 1 Project setup and Dependencies
- [Done] Step 2 Defining Models and Prompts
- [Done] Step 3 Firecrawl logic written
- [Done] Step 4 Building Core services
- [Done] Step 5 Designing the LangGraph Workflow

## Conclusion:

I had planned to achieve {this this}. I think I have/have-not achieved the conclusion satisfactorily. The reason for your satisfaction/unsatisfaction.

----------

# Added instructions:

- This is a `solo assignment`. Each of you will work alone. You are free to talk, discuss with chatgpt, but you are responsible for what you submit. Some students may be called for viva. You should be able to each and every line of work submitted by you.

- `commit` History maintenance.
  - Fork this repository and build on top of that.
  - For every step in your plan, there has to be a commit.
  - Change [TODO] to [DONE] in the plan, before you commit after that step. 
  - The commit history should show decent amount of work spread into minimum two dates. 
  - **All the commits done in one day will be rejected**. Even if you are capable of doing the whole thing in one day, refine it in two days.  
 
 - Deadline: Dec 2nd, Tuesday 11:59 pm


# Grading: total 25 marks

- Coverage of most of topics in this class: 20
- Creativity: 5
  
