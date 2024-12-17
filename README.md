# RAG-based Question Answering for Multi-Release Systems: A Case Study at Ciena

## Abstract

We propose QAMR, a novel RAG-based question answering chatbot for technical documents associated with multi-release systems. Retrievers in traditional RAG systems encounter significant challenges with these documents because multiple versions coexist, each containing distinct yet overlapping content. QAMR addresses these challenges through a novel combination of a pre-processing step, a query rewriting process that generates multiple standalone queries for a given user query, and a state-of-the-art context reranking strategy. In addition, QAMR provides a novel dual-chunking approach to address a major practical limitation of RAG systems regarding the choice of an optimal chunk size. We evaluate QAMR using two industry datasets, one from Ciena and one publicly available. Our evaluation shows that QAMR outperforms a baseline RAG-based chatbot without dual-chunking by achieving 91\% answer correctness and 90\% retrieval accuracy, representing average improvements of 17\% and 12\% over the baseline, respectively.

## Getting Started


* **Code for the QAMR:** Located in the `Code-QAMR` directory, running `main.py` generates responses for all questions listed in the provided `.xlsx` file. The `main-time.py` script not only produces these responses but also generates a file detailing the time each specific component of the chatbot takes to respond to each question. After all questions have been addressed, the `main-evaluation.py` script utilizes the generated response file to execute the evaluation pipeline, computing all relevant metrics for the generated responses.

* **Code for the Baseline:** Found in the `Code-Baseline` directory, the `main-baseline.py` script functions similarly to the QAMR's `main.py`, generating responses for the questions provided in the `.xlsx` file using the Baseline approach. Additionally, `main-time-baseline.py` generates an output file that records the time each component takes to answer each question from the Baseline. Finally, akin to QAMR, running `main-evaluation.py` with the generated response file initiates the evaluation process.

* **Results of the Experiments for Research Question 1 (RQ1):** Stored in the `RQ1` directory, this section includes comprehensive results, embeddings, and evaluation metrics for `Contextual Precision (cp)`, `Contextual Recall (crec)`, `Contextual Relevancy (crel)`, `Answer Relevancy (arel)`, `Faithfulness (f)`, and `Answer Correctness (ac)`. These metrics cover all ten runs across both datasets using both QAMR and Baseline methods. Please note that the results for the Ciena dataset have been redacted to maintain confidentiality. To visualize the data and perform statistical tests, run the `main.py` file located within each dataset's subdirectory.

* **Results of the Experiments for Research Question 2 (RQ2):** Located in the `RQ2` directory, this section contains the final generated responses and the time taken to produce each answer. It includes runtime data for five runs across two datasets, utilizing both QAMR and the Baseline approaches.

* **Prompts:** All prompts used in QAMR are compiled in the `prompts.pdf` file. This document encompasses prompts for `Query Rewriting`, `Context Reduction`, `Context Selection`, and `Answer Generation`. Additionally, it includes the prompts employed in the `Answer Correctness` metric for evaluation purposes.

* **REQuestA Dataset:** The `REQuestA_Dataset` directory contains PDF files for the REQuestA dataset, along with a dataset comprising 159 question-and-answer pairs used to test the chatbot.