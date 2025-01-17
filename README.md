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
We recommend downloading in advance any datasets you wish to explore with your teammates to save time and reduce stress on the on-site WiFi. Some suggested open-source datasets are listed below [CREATE LINK!]. 

[!NOTE]
The choice of dataset is an excellent opportunity to showcase your creativity! 

It may help to choose datasets whose vector embeddings have been pre-calculated, or else to calculate and save them in advance. Otherwise, you can calculate embeddings for the dataset locally during the hackathon, or use free credits provided by our sponsors to perform this embedding in the cloud [CREATE LINK!].

### Download Foundation Models
We also recommend downloading in advance any 

As an alternative 

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

You will have from 10am - 5.30pm to develop a submission with your team. Before 5.30pm

### Prompt


## Submission Instructions

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
