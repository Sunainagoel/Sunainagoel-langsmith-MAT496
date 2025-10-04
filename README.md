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


**Video 3:** This lesson introduced more flexible tracing options beyond the default @traceable decorator. I explored:

  with trace(): for more controlled, manual tracing.

  wrap_openai: which automatically tracks OpenAI calls.

  Built-in LangChain/LangGraph tracing: which captures internal components automatically.

The key takeaway was that you can mix these tracing methods depending on how much control or automation you want. For instance, with trace() lets you trace only a portion of a function, while decorators wrap the whole thing.
**Tweaking:** I designed a new RAG pipeline using Wikipedia data (Climate Change) and applied each tracing method to different parts of the process and added questions of my own.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/alternative_tracing_methods.ipynb 
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module%201/alternative_tracing_methods.ipynb


**Video 4:** Here, I learned how to structure traces to reflect back-and-forth conversations — not just one-off LLM calls. Using a shared thread_id, we can group multiple traces as part of a single conversation. This is shown visually in the LangSmith “Thread View,” which looks and feels a lot like real chatbot transcripts.
**Tweaking:** I added additional questions of my own to extend the conversation and included more inputs and responses, which allowed me to see how the thread evolved in LangSmith. I also attached screenshots that clearly show how all these exchanges are grouped together in the LangSmith interface.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_1/conversational_threads.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module%201/conversational_threads.ipynb


### Module 2:
**Video 1:** This video explained why datasets are so important when testing LLM applications — especially since these models often give different outputs for the same input. Datasets help us track if our changes actually improve results. In LangSmith, a dataset is just a list of examples (input + expected output). You can also tag datasets to version them or split them for separate testing.
**Tweaking:** I created new traces and added them to the dataset using code and also explored how to manage and edit datasets directly on the LangSmith website. I also made a completely new dataset using code and populated it with examples.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/dataset_upload.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/dataset_upload.ipynb


**Video 2:** Evaluators are the tools used to score how well our model performed. They compare the model’s output with the expected output in a dataset and return a score (like accuracy, etc). We can either code our own evaluator or use an LLM to judge the quality of the output.
**Tweaking:** I added some more examples to test how the evaluator’s score changes with better or worse outputs. Then I created my own evaluator using LLM-as-a-judge to score helpfulness from 1 to 5 — where 1 means unhelpful and 5 means very helpful and informative. I tested it with multiple examples.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/evaluators.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/evaluators.ipynb


**Video 3:** This part showed how to bring datasets and evaluators together to run experiments. When we run an experiment, our model is tested on each example in the dataset and gets evaluated automatically. We can control which examples we run it on (e.g. specific tags, splits, or even selected examples). We can also run multiple times (repetitions), run them faster (using concurrency), or attach metadata like model names to track results better.
**Tweaking:** I ran the given experiments on my own custom one(MAT496). I made a split and ran on it as well. 

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/experiments.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/experiments.ipynb


**Video 4:** LangSmith gives a really clean UI to visualize the results of our experiments. You get summary charts, filters, and the ability to inspect specific examples and their traces. Evaluators also have their own trace, which can be explored. You can also compare different experiments side by side using metrics or graphs.
**Tweaking:** Since no code was provided, I uploaded a Jupyter notebook where I added screenshots of my experiments and how I used the LangSmith interface to analyze the results.

**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/analyzing_experiment_results.ipynb
