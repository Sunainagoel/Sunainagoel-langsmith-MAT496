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


**Video 5:** Sometimes, evaluating model outputs individually doesn't give clear insights — this is where pairwise evaluations help. In this setup, two model outputs for the same input are compared side by side, and we decide which one is better. It's a more direct way to compare models.

**Tweaking:** I included screenshot of the “good vs bad” comparison and added it to my notebook as a reference to understand how it works.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/pairwise_experiments.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/pairwise_experiments.ipynb


**Video 6:** Some metrics — like precision, recall, and F1 score — can't be calculated on single examples. These are called summary evaluators. They evaluate the full experiment and give overall scores. This gives a more complete picture of how our model is doing.

**Tweaking:** I uploaded a screenshot of the experiment results where the F1 score were already calculated by LangSmith.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_2/summary_evaluators.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module2/summary_evaluators.ipynb


### Module 3:
**Video 1:** LangSmith's Playground is a great place to develop prompt engineering. While prompts are typically merely hard-coded strings, working with prompt templates provides flexibility by allowing you to insert variables during runtime. Within the Playground, you can construct and test prompts, compare results, experiment with your data, and even include tools. It also allows you to load data and specify output schemas so you can keep results uniform and structured. All in all, it's a powerful sandbox for experimenting with LLMs.

**Tweaking:** Included screenshots to go through the main features of the LangSmith Playground. I tried new prompt templates with a given dataset and compared the responses of two LLMs — OpenAI and Groq — under the same prompts. I checked for accuracy by running repetitions and also developed my own database, running it with other prompt templates to watch variations in output.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/playground_experiments.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module3/playground_experiments.ipynb


**Video 2:** In LangSmith, the Prompts Hub serves as a central place to design, save, and manage prompt templates. Once a prompt is created, you can commit changes, push new templates from your code, or pull templates (including specific versions) back into your project. Each prompt template includes variables that are filled in at runtime, model configurations, and an optional output schema to ensure the output follows a consistent format.

**Tweaking:** I added annotated screenshots to make sure to clearly describe what I discovered on the LangSmith portal. I made my own prompt in the Prompts Hub, pulled it without the LLM model, and tested them by asking tailored questions. I also asked my own questions on the existing prompt template.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/prompt_hub.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module3/prompt_hub.ipynb


**Video 3:** This video covered a full walkthrough of how to use the Playground and Prompts Hub to iteratively improve a prompt within an application. One key takeaway was that once a prompt is linked through LangSmith, any edits or new commits made directly in the interface are automatically reflected in the application — meaning there's no need to manually update the code each time. This makes the iteration process much more efficient and flexible.

**Tweaking:** We ran multiple prompt variations to verify that the instructions were being followed correctly and the outputs were consistent and aligned with expectations.

**Source code:** https://github.com/langchain-ai/intro-to-langsmith/blob/main/notebooks/module_3/prompt_engineering_lifecycle.ipynb
**My code:** https://github.com/Sunainagoel/Sunainagoel-langsmith-MAT496/blob/main/module3/prompt_engineering_lifecycle.ipynb
