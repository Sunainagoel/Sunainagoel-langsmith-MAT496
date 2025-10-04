# Sunainagoel-langsmith-MAT496
### Module 1:
**Video 1:** In this lesson, I learned about tracing which is a way to observe exactly how an LLM application executes underneath. Tracing serves as a map of execution as it shows every call to a function as well as its input and output during sequential execution. I learned traces consist of runs including a root run and any sub-components that your application has. Using the @traceable decorator, you can get started in just one line, and you’re now capturing runtime information that can be very valuable.
**Tweaking:** I added custom metadata, including dynamic values during execution. I modified the original code with my own questions and traced outputs to better understand what’s going on step by step.
**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/tracing_basics.ipynb 
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module%201/tracing_basics.ipynb

**Video 2:** This video went deeper into the idea that not all traces are the same. LangSmith lets you categorize each traced function by its role: llm, retriever, tool, chain, etc. This helps organize your trace logs and makes debugging much easier because each piece of the workflow is labeled clearly.
**Tweaking:** I created a new tool function (currency_converter) and traced it as a tool type. I also adjusted how outputs are generated in the llm section to experiment with formatting.
**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/types_of_runs.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module%201/types_of_runs.ipynb
