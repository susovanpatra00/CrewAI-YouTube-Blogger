# CrewAI YouTube Blogger

## Project Overview

This project is designed to automate the creation of compelling blog posts from YouTube videos, particularly in the fields of AI, Data Science, Machine Learning, and Generative AI. The project employs a team of virtual agents (powered by CrewAI) that conduct research and write articles based on the content extracted from specific YouTube channels. 

## Key Components

### 1. **Agents**
   - **Researcher Agent (`researcher`)**: Focuses on understanding videos related to a specific topic and providing relevant suggestions. It utilizes tools and memory to enhance its capabilities.
   - **Writer Agent (`writer`)**: Specializes in crafting engaging and accessible narratives from the information provided by the researcher. This agent is responsible for creating tech stories that simplify complex topics.

### 2. **Tasks**
   - **Research Task (`research_task`)**: Involves identifying key trends and insights from YouTube videos related to the given topic. The output is a comprehensive report summarizing the findings.
   - **Writing Task (`write_task`)**: Focuses on composing an insightful and engaging article based on the research findings. The article is formatted in markdown and designed to be easy to understand and appealing to readers.

### 3. **Tools**
   - **YouTube Channel Search Tool (`tool`)**: A tool that searches for content on a specific YouTube channel. In this case, the search is targeted at the channel handle `@krishnaik06`.

### 4. **Crew Configuration**
   - **Crew (`crew`)**: A group of agents working together in a sequential process to accomplish the tasks of researching and writing. The crew is configured to share memory, cache results, and manage execution with a rate limit.

## How It Works

1. **Agent Setup**: The `agents.py` script defines the roles and goals of the researcher and writer agents, equipping them with the necessary tools and memory capabilities.

2. **Task Definition**: The `task.py` script outlines the specific tasks that each agent will perform. The researcher agent is responsible for analyzing YouTube videos, while the writer agent creates the final blog post based on the research.

3. **Execution**: The `crew.py` script orchestrates the process by forming a crew of agents and executing the tasks sequentially. The inputs for the task are provided, and the output is generated in the form of a blog post saved as `new-blog-post.md`.

4. **Configuration**: The `app.py` script handles the configuration of the language model used by the agents, sets up environment variables, and initializes tools like the `HuggingFaceHub` model.

## How to Use

### Prerequisites

- Python 3.8+
- Required Python libraries: `crewai`, `dotenv`, `huggingface_hub`, `langchain_community`, `crewai_tools`
- API keys for HuggingFace Hub and OpenAI (optional).

### Setup

1. **Install Dependencies**: Run `pip install -r requirements.txt` to install the necessary packages.
2. **Set Environment Variables**: Create a `.env` file and set your API keys for HuggingFace Hub and OpenAI (if used).
3. **Run the Application**: Execute the `crew.py` script to start the process and generate a blog post from YouTube video content.

### Example Usage

```bash
python crew.py
```

This command will execute the predefined tasks and produce a blog post on a specified topic. The output will be saved in `new-blog-post.md`.

## Customization

- **Changing the Topic**: Modify the `inputs={'topic': 'Your Topic Here'}` line in `crew.py` to change the focus of the research and writing tasks.
- **Targeting a Different YouTube Channel**: Update the `youtube_channel_handle` in `tools.py` to search for videos from a different channel.
- **Adjusting the Language Model**: Configure the `repo_id` in `app.py` to use a different language model from the Hugging Face Hub.

## Future Enhancements

- Add support for more complex multi-agent interactions and delegation capabilities.
- Integrate additional tools for broader video content analysis.
- Expand the project to cover a wider range of topics beyond AI and tech.
