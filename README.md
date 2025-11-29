# Automated_AI_Newsletter_Agent
This notebook showcases an end-to-end multi-agent system built using the Google Agent Development Kit (ADK) to automatically research, coordinate, and generate a professional weekly newsletter on Artificial Intelligence and Machine Learning. The system demonstrates advanced agentic capabilities, tool use, and complex sequential orchestration.


Key Features and Capabilities
Four Specialized Agents: The system is composed of four dedicated research agents and one final formatting agent, each equipped with specific tools and instructions for highly focused data collection.
Diverse Tool Integration: Integrates the official Google Search tool, a custom Python function for the YouTube API, a custom Python function for the ArXiv API, and the MCP Toolset for GitHub data extraction.
Sequential Orchestration: A SequentialAgent acts as the RootOrchestrator, managing the flow from data gathering to final content generation.

Agent Workflow and Process Steps
The automation follows a strictly defined, two-stage sequential workflow managed by the RootOrchestrator:

Stage 1: Data Gathering (Coordinated by ResearchCoordinator)
News & Articles (ResearchAgent_google):
Tool: Google Search
Task: Searches for the top 4-5 trending AI/ML news articles within the specified date range, extracts headlines, summaries, and complete, verified URLs.

Trending GitHub Repositories (ResearchAgent_GitHub_MCP):
Tool: MCP Toolset (mcp-github-trending)
Task: Identifies the 3-5 most significant open-source AI/ML projects trending on GitHub for the last week, extracting repository details, star counts, and direct links.

Must-Watch Videos (ResearchAgent_YouTube):
Tool: Custom FunctionTool (Python function calling YouTube Data API v3)
Task: Finds the top 3-5 trending AI-related videos/editorials from the last week, extracting video titles, creators, and watch links.

Research Papers (ResearchAgent_ArXiv):
Tool: Custom FunctionTool (Python function calling ArXiv API)
Task: Executes multiple targeted searches to find and summarize the top 5 most impactful and recent AI/ML research papers, including authors, abstracts, and direct PDF links.

Stage 2: Content Generation (Handled by NewsletterFormatter)
Consolidation: The NewsletterFormatter agent receives the structured outputs from all four research agents.

Formatting and Editing: The agent applies a professional, fixed newsletter template, structuring the raw data into coherent sections: Top News, Trending Projects, Must-Watch Videos, and Research Highlights.

Final Polish: Writes a compelling introduction, smooth transitions, and a concise Key Takeaways summary, ensuring a professional and engaging final product.
