# Multi-task Memory Networks for Category-speciﬁc Aspect and Opinion Terms Co-extraction

## Motivation

- Generate more detailed and structured opinion analysis.
- Provide a more useful end-to-end analysis, which can extracte and classify aspect/opinion terms simultaneously.
- The pipeline approach may suffer from error propagation from the extraction phrase to classification phrase.

## Idea

- Aspect/opinion terms extraction for a specific category is considered as a task, and all the tahsks are learned jointly by exploring commonalities and relationships among them.
- Consider terms extraction for each specific category as an individual task, and design a memory network to co-extract aspect terms and opinion terms within each task via dual label propagation.
- Multi-task learning aims to imporve generalization for each individual task by exploiting relatedness among different tasks.

## Model

- 4 main components in our proposed deep architecture (Multi-task Memory Networks, MTMNs):
    - **Dual Propagation Memory Network** to co-extract aspect and opinion terms for each category
    - **Shared Tensor Decomposition** to model the commonalities of syntactic relations among different categories by sharing the tensor parameters
    - **Context-aware Multi-task Feature Learning**, which aims to jointly learn features among categories through constructing conterxt-aware task similarity matrices
    - **Auxiliary Task**, which create an auxiliary task to predict overall sentence-level category labels to assist token-level prediction tasks.

## Evaluation

DataSet:
- S1 (SemEval 2015) contains reviews from the restaurant domain.
- S2 (SemEval 2016) contains reviews from the restaurant domain.
- S3 (SemEval 2014) contains reviews from the laptop domain.

| ModelName | S1-ASC | S1-OPC | S1-AS | S1-OP | S2-ASC | S2-OPC | S2-AS | S2-OP | S3-ASC | S3-OPC | S3-AS | S3- OP |
| --------- | ------ | ------ | ----- | ----- | ------ | ------ | ----- | ----- | ------ | ------ | ----- | ------ |
| NLANG     | 42.90  | -      | 67.11 | -     | 52.61  | -      | 72.34 | -     | -      | -      | -     | -      |




## Contribution

- Provide a model that can achieve both extraction and categorization for terms simultaneously.

## Future work

## My thought

- It is hard to understand dual propagation