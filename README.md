# Women in AI Hackathon
[Registration Page](https://lu.ma/women-in-tech), [Discord (TODO)](...)

## Introduction
Welcome to the first Women in AI Hackathon, hosted by Zilliz [TODO] and sponsored by TwelveLabs, Arize AI, OmniStack, and StreamNative.

This repo provides all required information for the day as well as serving as the starting point for your submission. Direct any questions to [Stefan Webb](mailto:stefan.webb@zilliz.com) before the day of the hackathon and to the [Discord channel]() or in-person mentors on the day.

## Before the Day
There a couple of items we recommend completing in advance of the hackathon:

### GitHub
Set up a GitHub account plus the necessary Git tooling on your system, if you have not already.

### Set Up Development Environment
Clone this repo and set up your development environment. Your environment must allow you to develop a solution within the constraints of the prompt, that is, developing a RAG application in Python using Milvus or Zilliz Cloud.

We recommend:
* [MiniConda](https://docs.anaconda.com/miniconda/)
* [VS Code](https://code.visualstudio.com/)

Please confirm that you can run the starter notebooks on your platform:
* ["Quickstart with Milvus Lite"](https://github.com/milvus-io/bootcamp/blob/master/bootcamp/tutorials/quickstart/quickstart.ipynb)
* ["Multimodal Retrieval with Amazon Reviews Dataset and LLVM Reranking"](https://github.com/milvus-io/bootcamp/blob/master/bootcamp/tutorials/quickstart/multimodal_retrieval_amazon_reviews.ipynb)

You may also wish to confirm that you can start and use a [Milvus Standalone deployment](https://milvus.io/docs/prerequisite-docker.md) locally and access the [free-tier of Zilliz Cloud](https://cloud.zilliz.com/signup).

### Download Datasets
We recommend downloading in advance any datasets you wish to explore with your teammates to save time and reduce stress on the on-site WiFi.

Here are some suggested open-source datasets:
* A
* B
* C

> [!NOTE]
> The choice of dataset and data modality is an excellent opportunity to showcase your creativity! 

It may help to choose datasets whose vector embeddings have been pre-calculated, or else to calculate and save them in advance. Otherwise, you can calculate embeddings for the dataset locally during the hackathon, or use [free credits provided by our sponsors](./CREDITS.md) to perform this embedding in the cloud.

### Download Foundation Models
We also recommend downloading in advance any foundation models you plan to use locally during the hackathon.

Here are some suggested open-source general-purpose foundation models:
*
*
*
And specialized fine-tuned models:
*
*
*
> [!NOTE]
> Multimodal models offer many avenues for creativity, and a technically sophisticated solution is likely to make use of several fine-tuned models for specific parts of the pipeline.

As an alternative, see here for [free credits provided by our sponsors](./CREDITS.md) to perform model inference.

## Schedule
* 8.30-9.00: Check-in, light breakfast
* 9.00-9.30: Kickoff
* 9:30-10.00: Team reveal and challenge recap
* **10.00: Let the Hacking Begin!**
* 12.00-13.00: Lunch and speakers
* 13.00-17.30: More Hacking!
* **17.30: Hard submission and code frieze**
* 17.30-18.00: Work on presentations
* 18.00-19.30: Showcase your project
* 19.30-20.00: Judges award prizes

## Let's Hack!
### Overview
At 9.30-10am, we will reveal the team assignment. Teams comprise 3-5 hackers of varying experience and backgrounds. Of course, you may negotiate a team change with your fellow hackers if you wish although encourage you to pair with people you have not previously met.

After settling on your teams, please decide on a team lead and post the team name and cloned GitHub repository address to the Discord channel.

You will have from 10am - 5.30pm to develop a submission with your team. Before 5.30pm perform your final submission to your cloned repo. **At this time, no further code changes will be considered by the judges.**

An additional time from 5.30-6.00pm is provided to work on your presentation (see submission instructions below). You can continue to push your slide deck to your GitHub repo until 6pm.

### Prompt
```
“Build a retrieval-augmented generation (RAG) system for one of the following applications:

* A recommender system;
* A question/answering system for a specialized domain;
* A product review summarizer;
* A personalized job recruiter; or,
* Something of your own imagination!

Your solution must run in Python, demo with a single Jupyter notebook, and use Milvus (any deployment type) as the underlying vector database.

You are restricted to using foundation models under 15B parameters and may use agentic steps in your RAG pipeline. Free credits from our sponsors are available for embedding and foundation model inference.”
```

## Submission Instructions
Your chosen team lead submits your team's project via their fork of this GitHub repo.

1. Between 9.30am - 10am, have your team lead submit to the Discord channel your:
    * team's name and members;
    * forked GitHub repo address for code submission; and,
    * link to a copy of the final presentation template on Google slides. 
2. 10am - 5.30pm: Hack, hack, hack! Submit your code via pushes to your forked GitHub repo throughout the day.
> [!IMPORTANT]
> Ensure your final code is submitted before 5.30pm!
3. 5.30pm - 6pm: Finalize your presentation slides.
4. 6pm - 7.30pm: Each team presents their project.
5. 7.30pm - 8pm: Judges announce results!

## Judging Criteria

The judges will rank the teams' submissions in 3 criteria, separately:
* creativity;
* technical sophistication; and,
* potential business impact.

In the spirit of RAG, the teams rankings will be combined into a single score per-judge with [Reciprocal Rank Fusion (RRF)](https://learn.microsoft.com/en-us/azure/search/hybrid-search-ranking).

The per-judge score of a team is,
```latex
k = 10
score = 1 / (rank_creativity + k) + 1 / (rank_technical + k) + 1 / (rank_business + k)
```
where the `rank` terms denote the team's ranking for a given judge and criterion. The final score per team is the average of team scores across judges. What this means is that the winning team must score highly across all 3 criteria with a consensus across judges.

We will provide a breakdown of team scores by final score and each criterion separately.

## Prizes
* First prize: ???
* Second prize: ???
* Third prize: ???

## Resources
* [Milvus documentation](https://milvus.io/docs)
* [Milvus Bootcamp tutorials](https://github.com/milvus-io/bootcamp/tree/master)

## Sponsors (Alphabetical Order)
[Insert company logos!]

### Gold
* [TwelveLabs](https://www.twelvelabs.io/)

### Silver
* [Arize AI](https://arize.com/)
* [OmniStack](https://omnistack.sh/)
* [StreamNative](https://streamnative.io/)

### ???
* [AWS](https://aws.amazon.com/)
* [Mistral](https://mistral.ai/)
