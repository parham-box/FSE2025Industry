# RAG-based Question Answering for Multi-Release Systems: A Case Study at Ciena

## Abstract

Companies regularly have to contend with multi-release systems, where several versions of the same software are in operation simultaneously. Question answering over documents from multi-release systems poses challenges because different releases have distinct yet overlapping content. Motivated by the observed inaccuracy of state-of-the-art question-answering techniques on multi-release system documents, we propose QAMR, a chatbot designed to answer questions across multi-release system documentation. QAMR  enhances traditional retrieval-augmented generation (RAG) to ensure accuracy in the face of highly similar yet distinct documentation for different releases. It achieves this through a novel combination of pre-processing, query rewriting, and context selection. In addition, QAMR  introduces a dual-chunking approach that addresses RAG's limitation of having to choose an optimal chunk size for both retrieval and answer generation. We evaluate QAMR  using two datasets: one from our industry collaborator, Ciena, and another from a public software-engineering benchmark. Our evaluation shows that QAMR  outperforms a baseline RAG-based chatbot without dual-chunking by achieving 88.5% answer correctness and 90% retrieval accuracy, which represent average improvements of 16.5% and 12% over the baseline, respectively. Furthermore, we demonstrate that our results strongly correlate with expert assessments, thereby validating our method for measuring accuracy.

## Getting Started

* **Code for the QAMR:** Located in the `Code-QAMR` directory, running `main.py` generates responses for all questions listed in the provided `.xlsx` file. The `main-time.py` script not only produces these responses but also generates a file detailing the time each chatbot component takes to respond to each question. After generating responses for all questions, the `main-evaluation.py` script uses the generated response file to execute the evaluation pipeline, computing all relevant metrics for the responses.

* **Code for the Baseline:** Found in the `Code-Baseline` directory, the `main-baseline.py` script functions similarly to QAMR's `main.py`, generating responses for the questions in the `.xlsx` file using the Baseline approach. Additionally, `main-time-baseline.py` creates an output file that records the time each component takes to answer each user query. Finally, similar to QAMR, running `main-evaluation.py` with the generated response file initiates the evaluation process.

* **Results of the Experiments for Research Question 1 (RQ1):** Stored in the `RQ1` directory, this section includes comprehensive results, embeddings, and evaluation metrics for `Contextual Precision (cp)`, `Contextual Recall (crec)`, `Contextual Relevancy (crel)`, `Answer Relevancy (arel)`, `Answer Faithfulness (f)`, and `Answer Correctness (ac)`. These metrics cover all ten runs across both datasets using both QAMR and Baseline methods. Please note that the evaluation results for the Ciena dataset only include the final results for each evaluation metric. All other information, as well as the `reason` and `error` columns from the evaluation metrics, have been redacted to maintain confidentiality. To visualize the data and perform statistical tests, run the `main.py` file located within each dataset's subdirectory.

* **Results of the Experiments for Research Question 2 (RQ2):** Located in the `RQ2` directory, this section contains the final generated responses and the time taken to produce each answer. It includes runtime data for five runs across two datasets, utilizing both QAMR and the Baseline approaches. Please note that only the time taken for each user query is available for Ciena documents, and all other information is redacted to maintain confidentiality.

* **Results of the Experiments for Section 5 (Section 5):** Located in the `Section5` directory, this section contains the evaluation results for a single run of QAMR on Ciena documents for `Contextual Precision (cp)`, `Contextual Recall (crec)`, `Contextual Relevancy (crel)`, `Answer Relevancy (arel)`, `Answer Faithfulness (f)`, and `Answer Correctness (ac)` metrics, compared with domain experts' assessments of the generated responses from that run. Ciena's domain experts marked adequate responses with `1` and inadequate responses with `0`. Run the `main.py` file to calculate the Pearson correlation and p-value between each evaluation metric and the domain experts' assessments. Please note that the evaluation results for this dataset only include the final scores for each evaluation metric, metric name, and the domain experts' assessment. All other information has been redacted to maintain confidentiality.

* **Prompts:** All prompts used in QAMR are compiled in the `prompts.pdf` file. This document includes prompts for `Query Rewriting`, `Context Reduction`, `Context Selection`, and `Answer Generation`. Additionally, it includes the prompts used in the `Answer Correctness` metric for evaluation purposes.

* **REQuestA Dataset:** The `REQuestA_Dataset` directory contains six PDF files for the REQuestA dataset, along with a dataset, `REQuestA-Cleaned-Dataset.xlsx`, comprising 159 question-and-answer pairs used to test the chatbot.
