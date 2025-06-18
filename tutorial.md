# Tutorial: LLMs_4_tweets
Please find the method of this tutorial at [https://git.gesis.org/bensmafx/llm-4-tweets](https://git.gesis.org/bensmafx/llm-4-tweets).


## Learning Objectives

By the end of this tutorial, you will be able to

- To use ChatGPT to annotate your tweets
- To run an evaluation to estimate an LLM's performance on the task


## Description
- This tutorial contains instructions on how to use ChaptGPT as example of an LLM to annotate tweets, using 0-shot prompting.
- Further a section explaining the evaluation and its output attached. 

## Target Audience (Difficulty level)
- This tutorial is aimed at beginners who want to use LLMs for social media post annotation.
- The evaluation however is directed towards data scientists with decent knowledge on interpreting performance metrics: Precision / Recall / IRR

## Prerequisites
Before you begin, you need to know the following technologies.
- Python, Jupyter notebooks
- LLMs

## Environment Setup

### Using LLMs for annotation
- Sign up with ChaptGPT at [https://chatgpt.com/](https://chatgpt.com/)

### LLM evaluation
To estimate an LLM's performance on your task you can perform an evaluation.

- Gather gold/ground truth annotations for a subset of the tweets, for example by using human annotators, for better reliability you should use at least thee annotators and 100 tweets
- Setup a Jupyter notebook server that meets the requirements stated in `READEME.md`
- Create and CD into a working folder in the document tree
- Place the `evaluate_annotation.ipynb` in the working folder


## Tutorial content

### Using LLMs for annotation
- Use a web browser to login to the ChatGPT web UI
- Start a new Chat
- Prepare some tweets for annotation for example in an Excel spreadsheet, the text is sufficient, further columns can store the annotations later on
- Adapt the prompt from `instructions_0-shot.docx` (OneDrive) to reflect your topic 
- Enter the prompt and the prepared tweets into ChatGPT. In order to not trigger the output limit you could feed ChatGPT the tweets in packages of five for example.
- Note down the results -> profit.

### LLM evaluation
To estimate an LLMs performance on your task you can also perform an evaluation.

- Store the annotations of humans and LLMs in a CSV file as can be seen in `preliminary_test_environment.csv`
- Create and cd to a working folder that is subject to a Jupyter Notebook server
- Make sure your notebook server meets the requirements as stated in README.md
- Add the evaluation script `evaluate_annotation.ipynb` and your prepared file to it. Alternatively you could also clone the repository
- Open the evaluation notebook, find the input data section and enter the path to your prepared file
- Run the notebook, it should complete with no errors
- Inspect the output

The evaluation will compile data about:

- Controversial tweets
- Agreement using multiple metrics like
  - [Fleiss' Kappa](https://en.wikipedia.org/wiki/Fleiss%27_kappa)
  - [Krippendorff's Alpha](https://en.wikipedia.org/wiki/Krippendorff%27s_alpha)
  - a<sub>0</sub> (ratio of pair-wise agreement)
- IRR between all annotators including ChatGPT
- Replace one of the humans with ChatGPT
- Pairwise IRR
- Compare ChatGPT to meta labelling approach
  - Majority vote
  - Only consider tweets with perfect agreement


## Sample Input and output data (Optional)
You can use the file `preliminary_test_environment.csv` as sample input for the annotation task by using its tweets. Also this file suites as sample input to the evaluation procedure.


## How to Use (Optional)
For the LLM as well for human annotators the prompt is decicise for the outcome of the experiment. 
At the given task of determinig the relevance of a tweet for a given topic we first need to answer the question of how to define the individual topic. 
Next we have to decide if we want a binary decision (relevant/not relevant) or if see relevance on a scale or spectrum. the latter can still be converted into a binary measure.
For annotors humans or classifiers we then have to formulate (simple) rules that help identifying the topic and also express a tweet's relevance towards it. 
This highly dependents on the nature of a topic e.g. broadness, media coverage, personal vs. public topics, controversies, involved persona, ...

Going for a single topic and using relevance on a scale proved as the most practical approach to think about the annotation task independently of what kind of annotation is eventually used.


## References
-- empty --


## Contact details
* Debanjali Biswas (firstname.lastname@gesis.org)
* Felix Bensmann (firstname.lastname@gesis.org)


## Disclaimer (Optional)
Work in progress

## Further Exploration (Optional)
- [Fleiss' Kappa](https://en.wikipedia.org/wiki/Fleiss%27_kappa)
- [Krippendorff's Alpha](https://en.wikipedia.org/wiki/Krippendorff%27s_alpha)

