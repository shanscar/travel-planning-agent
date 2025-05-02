# Travel Planning Assistant

A sophisticated travel planning application built with AutoGen that orchestrates a team of specialized AI agents to create comprehensive, personalized travel itineraries.

## Overview

This application leverages the power of multiple AI agents, each with specific expertise, to collaborate on building travel plans. The system uses a structured workflow to gather information, research destinations, and generate detailed itineraries with local insights and language tips.

## Features

- **Multi-agent collaboration** - Specialized agents work together to create comprehensive travel plans
- **Web research capabilities** - Integrates Google search and webpage fetching to provide up-to-date information
- **Local expertise** - Recommends authentic experiences and hidden gems
- **Language assistance** - Provides relevant phrases and communication tips for travelers
- **Structured itineraries** - Generates day-by-day plans with clear sections and practical information

## Agents

The system includes the following specialized agents:

- **Planner Agent** - Creates the initial travel plan based on user requirements
- **Local Agent** - Enhances the plan with authentic local experiences and recommendations
- **Language Agent** - Adds language and communication tips specific to the destination
- **Travel Summary Agent** - Integrates all information into a cohesive final plan
- **User Proxy** - Represents the traveler seeking assistance

## Requirements

- Python 3.7+
- AutoGen framework
- OpenAI API key (for GPT-4o access)

## Installation

```bash
pip install autogen-agentchat autogenstudio
```

## Usage

```python
import asyncio
from autogen_agentchat.agents import AssistantAgent, UserProxyAgent
from autogen_agentchat.conditions import MaxMessageTermination, TextMentionTermination
from autogen_agentchat.teams import SelectorGroupChat
from autogen_agentchat.ui import Console
from autogen_ext.models.openai import OpenAIChatCompletionClient
from autogenstudio.gallery.tools import google_search_tool, fetch_webpage_tool

# Run the main function
asyncio.run(main())
```

## Example

The application can handle travel planning requests like:

```
"I'm planning a 10-day trip to Japan in April with my family (2 adults, 2 teenagers). 
We're interested in experiencing both traditional culture and modern attractions. 
We enjoy food experiences, light hiking, and interactive museums. Our budget is mid-range. 
We don't speak Japanese. Please help create a detailed travel plan."
```

## How It Works

1. The user provides their travel requirements and preferences
2. The **Planner Agent** develops an initial itinerary based on the request
3. The **Local Agent** enhances the plan with authentic local experiences
4. The **Language Agent** adds relevant language and communication tips
5. The **Travel Summary Agent** integrates all information into a comprehensive final plan
6. The user is only prompted for input when critical decisions or clarifications are needed

## Flow Control

The agent collaboration is managed by a selector system that follows this process:
1. Planner agent develops the initial travel plan
2. Local agent enhances with authentic experiences
3. Language agent adds communication tips
4. Summary agent creates the final comprehensive plan

The system minimizes unnecessary user involvement, only requesting input for major decision points or clarifications.

## Customization

You can modify the agents' system messages or add additional specialized agents to enhance the planning capabilities for specific travel needs.
